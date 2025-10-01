# Project Title: Application Load Balancer with Cloud Armor (GSP215) - End-to-End Build, Test, and Denylist

## Project Objective

Build a global external **Application Load Balancer** with dual-stack (IPv4/IPv6) frontends and regional backends (us-west1 and europe-west4). Stress-test from a third location (europe-west1-c) and **denylist** the load source with **Cloud Armor**.

---

## Project Description (with exact commands)

![Application Load Balancer with Cloud Armor](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Application%20Load%20Balancer%20with%20Cloud%20Armor-01.jpg)

### 1) Fetch and run the lab helper script from GitHub

![Application Load Balancer with Cloud Armor](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Application%20Load%20Balancer%20with%20Cloud%20Armor-02.jpg)

You used two equivalent ways to download the same script and run it under a custom name.

![Application Load Balancer with Cloud Armor](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Application%20Load%20Balancer%20with%20Cloud%20Armor-03.jpg)

**Option A — download → rename → run**

```bash
curl -LO raw.githubusercontent.com/prateekrajput08/Arcade-Google-Cloud-Labs/refs/heads/main/Application%20Load%20Balancer%20with%20Cloud%20Armor/TechCode.sh

mv TechCode.sh AmeinBiography.sh   # rename file

chmod +x AmeinBiography.sh
./AmeinBiography.sh
```

**Option B — save directly as the new name → run**

```bash
curl -Lo AmeinBiography.sh raw.githubusercontent.com/prateekrajput08/Arcade-Google-Cloud-Labs/refs/heads/main/Application%20Load%20Balancer%20with%20Cloud%20Armor/TechCode.sh

chmod +x AmeinBiography.sh
./AmeinBiography.sh
```

> Notes
> • Backends target regions: **us-west1**, **europe-west4**.


![Application Load Balancer with Cloud Armor](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Application%20Load%20Balancer%20with%20Cloud%20Armor-04.jpg)


> • Stress client zone: **europe-west1-c**.

![Application Load Balancer with Cloud Armor](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Application%20Load%20Balancer%20with%20Cloud%20Armor-05.jpg)

---

### 2) Create the stress-test VM (siege-vm) in europe-west1-c

```bash
# set project (auto from lab credentials)
PROJECT=$(gcloud config get-value project)

# create the siege-vm instance in europe-west1-c
gcloud compute instances create siege-vm \
  --zone=europe-west1-c \
  --machine-type=e2-micro \
  --image-family=debian-12 \
  --image-project=debian-cloud \
  --boot-disk-size=10GB \
  --boot-disk-type=pd-balanced
```

**Connect and install siege**

```bash
gcloud compute ssh siege-vm --zone=europe-west1-c

sudo apt-get -y update
sudo apt-get -y install siege
```

---

### 3) Exercise the Load Balancer

Replace `[LB_IP_v4]` with the IPv4 address of your load balancer.

```bash
export LB_IP=[LB_IP_v4]
siege -c 150 -t120s http://$LB_IP
```

---

### 4) Capture the siege-vm public IP ([SIEGE_IP])

```bash
gcloud compute instances describe siege-vm --zone=europe-west1-c \
  --format='value(networkInterfaces[0].accessConfigs[0].natIP)'
```

---

### 5) Create and attach a Cloud Armor denylist that blocks siege-vm

```bash
gcloud compute security-policies create denylist-siege \
  --description="Block siege-vm IP" \
  --global

gcloud compute security-policies rules create 1000 \
  --security-policy=denylist-siege \
  --src-ip-ranges=[SIEGE_IP] \
  --action=deny-403

gcloud compute backend-services update http-backend \
  --global \
  --security-policy=denylist-siege
```

**Re-test from siege-vm (expect 403 or blocked traffic)**

```bash
curl http://$LB_IP
# (Optional) try siege again: it should be blocked.
```

![Application Load Balancer with Cloud Armor](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Application%20Load%20Balancer%20with%20Cloud%20Armor-06.jpg)

---

## Conclusion

I stood up a **global external Application Load Balancer** with dual frontends, regional managed backends, and validated intelligent traffic steering under load. Then I **denylisted** the stress source using **Cloud Armor**, confirming protection at the edge with a 403 response and blocked siege traffic.

---

## Project URL
***Google-Cloud***: ***[Application Load Balancer with Cloud Armor](https://www.cloudskillsboost.google/focuses/1232?parent=catalog)***     

### Supporting Document  

* GitHub Repository script:
  ***[GitHub@prateekrajput08](https://raw.githubusercontent.com/prateekrajput08/Arcade-Google-Cloud-Labs/refs/heads/main/Application%20Load%20Balancer%20with%20Cloud%20Armor/TechCode.sh)***
  
---

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)
- **Contributor script author**: **@prateekrajput08** (GitHub) 
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions
- **Technologies**: **Google Cloud Application Load Balancing**, **Cloud Armor**, **Compute Engine**, **Managed Instance Groups**, **Debian** (siege client)
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  

---
