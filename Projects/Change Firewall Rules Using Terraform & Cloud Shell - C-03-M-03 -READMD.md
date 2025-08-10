# Change Firewall Rules Using Terraform & Cloud Shell

## Overview
Use Terraform in Google Cloud Shell to deploy a Virtual Private Cloud (VPC) and firewall rules, then modify those rules as needed. This process follows a real lab scenario for **Cymbal Bank's banking app infrastructure**.

---

## Prerequisites
- Temporary Google Cloud credentials from the lab
- Access to Google Cloud Console
- Cloud Shell (Terraform pre-installed)

---

## Step-by-Step Solution

### Step 0 — Start Lab & Sign In
1. Click **Start Lab**.
2. Open Google Cloud Console with lab credentials.
3. Accept terms, skip recovery, skip free trials.

---

### Step 1 — Activate Cloud Shell
1. Click **Activate Cloud Shell** in Console.
2. Click **Continue** and wait for initialization.

---

### Step 2 — Clone the Terraform Repo
```bash
cloudshell_open --repo_url "https://github.com/terraform-google-modules/docs-examples.git" \
  --print_file "./motd" \
  --dir "firewall_basic" \
  --page "editor" \
  --tutorial "./tutorial.md" \
  --open_in_editor "main.tf" \
  --force_new_clone
ls
cat main.tf
```
**Expected main.tf contents:**
- Creates VPC: `test-network-${local.name_suffix}`
- Creates firewall: `test-firewall-${local.name_suffix}`
- Allows `icmp` and `tcp` ports `80`, `8080`, `1000-2000`

---

### Step 3 — Set Project & Initialize Terraform
```bash
export GOOGLE_CLOUD_PROJECT=PROJECT_ID
gcloud config set project "$GOOGLE_CLOUD_PROJECT"
terraform init
```
Expected: “Terraform has been successfully initialized!”

---

### Step 4 — Deploy VPC & Firewall
```bash
terraform apply
```
Type:
```
yes
```
Expected:  
`Apply complete! Resources: 3 added, 0 changed, 0 destroyed.`

---

### Step 5 — Verify Resources
**Console:**  
- Navigation → **VPC network** → **VPC networks** → find `test-network-*`
- Click it → Firewalls → confirm rules match config

**CLI:**
```bash
gcloud compute networks list
gcloud compute firewall-rules list --filter="name~^test-firewall-"
```

---

### Step 6 — Modify Firewall Rules
Edit `main.tf` → examples:

**Example A: Add SSH (22), remove 8080**
```hcl
allow {
  protocol = "tcp"
  ports    = ["22", "80", "1000-2000"]
}
```

**Example B: Deny Telnet (23)**
```hcl
deny {
  protocol = "tcp"
  ports    = ["23"]
}
```

**Example C: Target specific instances**
```hcl
target_tags = ["web-server"]
```
(Apply tags to VMs to match.)

---

### Step 7 — Reapply Changes
```bash
terraform plan
terraform apply
```
Type `yes` when prompted.

---

### Step 8 — Verify Updates
```bash
gcloud compute firewall-rules describe test-firewall-UNIQUE_ID \
  --format="yaml(name,allowed,denied,sourceRanges,targetTags,priority,direction)"
```

---

### Step 9 — Cleanup
```bash
terraform destroy
```
Type `yes` when prompted.  
Click **End Lab** in the lab interface to close the environment.

---

## Example Original `main.tf`
```hcl
resource "google_compute_network" "test_network" {
  name = "test-network-${local.name_suffix}"
}

resource "google_compute_firewall" "test_firewall" {
  name    = "test-firewall-${local.name_suffix}"
  network = google_compute_network.test_network.name

  allow {
    protocol = "icmp"
  }

  allow {
    protocol = "tcp"
    ports    = ["80", "8080", "1000-2000"]
  }
}
```

---

## Key Points
- Protocols modified: **icmp, tcp**
- Always run `terraform plan` before `apply`
- Restrict `source_ranges` for better security
- Use `target_tags` to apply rules to specific resources

---
