# Project Title: **Analyze Google Cloud Audit Logs with BigQuery**  

---

## Project Objective
The main goals are:
- Generate user activity to simulate malicious actions.
- Export audit logs from Cloud Logging to BigQuery.
- Use Logs Explorer and BigQuery to analyze suspicious events.
- Answer the key question: **Who did what, where, and when?**

---

## Scenario: Cymbal Bank
Cymbal Bank had migrated to a hybrid cloud environment. Shortly after, a high-severity alert flagged unauthorized access to resources.  
I shadowed a senior Incident Responder to understand the investigation process. Two accounts were used:

- **User 1**: Simulated the malicious activity.  
- **User 2**: Investigated the logs.

---

## Setup
I began by:
- Opening Google Cloud Console.
- Activating Cloud Shell, verifying account and project with:

```bash
gcloud auth list
gcloud config list project
```

---

## Task 1 — Generate Account Activity (User 1)
I created and deleted resources to generate logs:

```bash
gcloud storage buckets create gs://$DEVSHELL_PROJECT_ID
echo "this is a sample file" > sample.txt
gcloud storage cp sample.txt gs://$DEVSHELL_PROJECT_ID
gcloud compute networks create mynetwork --subnet-mode=auto
export ZONE=$(gcloud compute project-info describe --format="value(commonInstanceMetadata.items[google-compute-default-zone])")
gcloud compute instances create default-us-vm --machine-type=e2-micro --zone=$ZONE --network=mynetwork
gcloud storage rm --recursive gs://$DEVSHELL_PROJECT_ID
```

![Account Activity](https://raw.githubusercontent.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/main/bar-graph-chart-image/Analyze%20audit%20logs%20using%20BigQuery-01.jpg)

This produced Admin Activity logs I could later analyze.

---

## Task 2 — Export the Audit Logs
Next, I exported logs into BigQuery:
- In Logs Explorer, I filtered for Cloud Audit logs.
- Created a **sink** named `AuditLogsExport`.
- Destination: a BigQuery dataset called `auditlogs_dataset`.
- Verified the sink in **Log Router**.  

**Query used in Logs Explorer:**
```text
logName = ("projects/PROJECT_ID/logs/cloudaudit.googleapis.com%2Factivity")
```

![Account Activity](https://raw.githubusercontent.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/main/bar-graph-chart-image/Analyze%20audit%20logs%20using%20BigQuery-02.jpg)


From this point onward, new logs would automatically export to BigQuery.

---

## Task 3 — Generate More Activity (User 1)
I then created additional events:

```bash
gcloud storage buckets create gs://$DEVSHELL_PROJECT_ID
gcloud storage buckets create gs://$DEVSHELL_PROJECT_ID-test
echo "this is another sample file" > sample2.txt
gcloud storage cp sample.txt gs://$DEVSHELL_PROJECT_ID-test
export ZONE=$(gcloud compute project-info describe --format="value(commonInstanceMetadata.items[google-compute-default-zone])")
gcloud compute instances delete --zone=$ZONE --delete-disks=all default-us-vm
gcloud storage rm --recursive gs://$DEVSHELL_PROJECT_ID
gcloud storage rm --recursive gs://$DEVSHELL_PROJECT_ID-test
```

![Account Activity](https://raw.githubusercontent.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/main/bar-graph-chart-image/Analyze%20audit%20logs%20using%20BigQuery-03.jpg)

These actions ensured more log entries for analysis.

---

## Task 4 — Switch to Second User (User 2)
I logged into the console as User 2 to simulate an **investigator role**.  
This account allowed me to review and analyze the logs without generating new ones.

---

## Task 5 — Analyze Admin Activity Logs (Logs Explorer)
Using Logs Explorer:
- I searched for **storage.buckets.delete** events.
- Filtered by service: `storage.googleapis.com`.
- Isolated bucket deletion entries.
- Expanded an entry to confirm the **principalEmail**, which revealed the user responsible: **User 1**.

**Query snippet:**
```text
logName=("projects/PROJECT_ID/logs/cloudaudit.googleapis.com%2Factivity")
protoPayload.serviceName="storage.googleapis.com"
protoPayload.methodName="storage.buckets.delete"
```

![Account Activity](https://raw.githubusercontent.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/main/bar-graph-chart-image/Analyze%20audit%20logs%20using%20BigQuery-04.jpg)

This clearly showed which account deleted the buckets.

---

## Task 6 — Use BigQuery to Analyze Audit Logs
Finally, I analyzed logs in BigQuery:
1. Confirmed `auditlogs_dataset` and permissions for the export service account.
2. Queried the tables `cloudaudit_googleapis_com_activity_*`.

**Query 1 — VM deletions (last 7 days):**
```sql
SELECT
  timestamp,
  resource.labels.instance_id,
  protopayload_auditlog.authenticationInfo.principalEmail,
  protopayload_auditlog.resourceName,
  protopayload_auditlog.methodName
FROM `auditlogs_dataset.cloudaudit_googleapis_com_activity_*`
WHERE PARSE_DATE('%Y%m%d', _TABLE_SUFFIX) BETWEEN DATE_SUB(CURRENT_DATE(), INTERVAL 7 DAY) AND CURRENT_DATE()
  AND resource.type = "gce_instance"
  AND operation.first IS TRUE
  AND protopayload_auditlog.methodName = "v1.compute.instances.delete"
ORDER BY timestamp, resource.labels.instance_id
LIMIT 1000;
```

![Account Activity](https://raw.githubusercontent.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/main/bar-graph-chart-image/Analyze%20audit%20logs%20using%20BigQuery-05.jpg)

**Query 2 — Bucket deletions (last 7 days):**
```sql
SELECT
  timestamp,
  resource.labels.bucket_name,
  protopayload_auditlog.authenticationInfo.principalEmail,
  protopayload_auditlog.resourceName,
  protopayload_auditlog.methodName
FROM `auditlogs_dataset.cloudaudit_googleapis_com_activity_*`
WHERE PARSE_DATE('%Y%m%d', _TABLE_SUFFIX) BETWEEN DATE_SUB(CURRENT_DATE(), INTERVAL 7 DAY) AND CURRENT_DATE()
  AND resource.type = "gcs_bucket"
  AND protopayload_auditlog.methodName = "storage.buckets.delete"
ORDER BY timestamp
LIMIT 1000;
```

![Account Activity](https://raw.githubusercontent.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/main/bar-graph-chart-image/Analyze%20audit%20logs%20using%20BigQuery-06.jpg)

These confirmed deletions made by User 1.

---

## Conclusion
To wrap up:
- I successfully exported and analyzed audit logs.
- Logs Explorer helped quickly isolate suspicious activities.
- BigQuery enabled structured analysis with SQL.
- The investigation clearly showed **User 1 deleting resources**.

This exercise demonstrated how audit logs, combined with BigQuery, are powerful tools for **incident response and security analysis**.

---

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  
