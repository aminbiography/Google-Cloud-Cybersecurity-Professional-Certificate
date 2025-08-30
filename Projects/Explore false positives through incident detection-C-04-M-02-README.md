# Explore False Positives Through Incident Detection (Google Cloud SCC)

---

## Project Objective

Recreate a **false positive** in Google Cloud, **analyze the SCC finding**, and **remediate** it—demonstrating incident detection, triage, and response skills using IAM service accounts and Security Command Center (SCC).

---

## Project Description

### Step 0 - Setup & Lab Hygiene
- Confirmed access to Google Cloud Console and Cloud Shell.

![Setup/Incognito](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-01.jpg)

---

### Step 1 - Create a Service Account (username1)
1. Console → **IAM & Admin → Service Accounts** → **+ Create Service Account**
2. Name: `test-account` → **Create and Continue**
3. Role: **Basic → Owner**
4. **Done** (verify `test-account` appears)

![Service Account Created](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-02.jpg)

---

### Step 2 - Create & Upload JSON Key
1. On `test-account` → **Manage keys**

![Key Created](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-03.jpg)  

 
2. **Add Key → Create new key → JSON → Create** (download JSON)
3. **Rename locally** to `test-account.json` *(ensure the filename matches the commands below)*

![Key Download](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-04.jpg)  
  
4. Open **Cloud Shell** → **More → Upload → Choose Files** → upload `test-account.json`


***Service Account JSON Key (Truncated for Security)***
```bash
{
  "type": "service_account",
  "project_id": "qwiklabs-gcp-03-xxxx",
  "private_key_id": "xxxx",
  "private_key": "-----BEGIN PRIVATE KEY-----\nMIIEvQIB...<redacted>...\n-----END PRIVATE KEY-----\n",
  "client_email": "test-account@qwiklabs-gcp-03-xxxx.iam.gserviceaccount.com",
  "client_id": "105250026009672560799",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token"
}
```


![Key Uploaded in Cloud Shell](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-05.jpg)  


![Key Uploaded in Cloud Shell](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-06.jpg)  

5. Verify upload:

```bash
ls
```

![ls Output](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-07.jpg)

---

### Step 3 - Trigger the False Positive
Configure environment variables and activate the service account with the key:

```bash
export PROJECT_ID=$(gcloud info --format='value(config.project)')
export SA_NAME="test-account@${PROJECT_ID}.iam.gserviceaccount.com"
gcloud auth activate-service-account ${SA_NAME} --key-file=test-account.json
```
Confirm the active identity:

```bash
gcloud auth list
```

![Activate SA](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-08.jpg) 

*Expected output shows `ACTIVE: *` next to the `test-account@<PROJECT_ID>.iam.gserviceaccount.com` entry.*

![gcloud auth list](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-09.jpg)  

---

### Step 4 - Grant Excessive Permissions to Second User
Set the second user and bind an Editor role (used later to analyze/remediate):

```bash
export STUDENT2="Google Cloud username 2"
gcloud projects add-iam-policy-binding $PROJECT_ID --member user:$STUDENT2 --role roles/editor
```

---

### Step 5 - Sign In as Second User (username2)
- **Add account** in the console → sign in with **username2** credentials from the Lab panel.

![Policy Binding](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-10.jpg)

---

### Step 6 - View & Analyze the SCC Finding
1. Console → **Security → Findings**
2. **Quick filters → Category → User managed service account key**
3. Open the **most recent** finding (by *Event time*).
4. Review **Summary**: severity, class, description, recommendations, and compliance.

![SCC Findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-11.jpg)  

![SCC Findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-12.jpg) 

---

### Step 7 - Remediate the Finding
1. Console → **IAM & Admin → Service Accounts**
2. Open `test-account`
3. **Keys** tab
4. **Delete** the JSON key (confirm deletion)

![Delete Key](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-13.jpg)

---

### Step 8 - Verify Resolution
- Return to **SCC → Findings** and refresh the query.
- Confirm the **User managed service account key** finding is resolved/closed or no longer active.

![Finding Resolved](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Explore%20false%20positives%20through%20incident%20detection-14.jpg)

---

## Conclusion

This project demonstrates my ability to:

- **Recreate** a real-world security scenario that triggers a false positive.
- **Analyze** findings in Security Command Center with attention to context.
- **Remediate** issues effectively by applying best practices in IAM and key management.

False positives are a common challenge in cloud security. By completing this lab, I reinforced the importance of distinguishing between harmless activity and real threats, ensuring efficient use of security resources.


---

## Command Line Summary

```bash
# Verify uploaded key
ls

# Set project and service account; activate with key to trigger SCC finding
export PROJECT_ID=$(gcloud info --format='value(config.project)')
export SA_NAME="test-account@${PROJECT_ID}.iam.gserviceaccount.com"
gcloud auth activate-service-account ${SA_NAME} --key-file=test-account.json

# Confirm active account
gcloud auth list

# Prepare second user and grant Editor to enable investigation/remediation
export STUDENT2="Google Cloud username 2"
gcloud projects add-iam-policy-binding $PROJECT_ID --member user:$STUDENT2 --role roles/editor
```

---

## Project Credit
- **Lab Activity & Prepared By**: **Mohammad Aminul Islam** (Cloud Security Analyst).  
- **Lab Source**: Google Cloud Security Command Center hands-on lab (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  
