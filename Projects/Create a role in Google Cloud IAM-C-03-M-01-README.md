# Project Title: **Create a Custom IAM Role in Google Cloud and Grant It to a User**

---

# Project Scenario

Cymbal Bank is migrating sensitive billing and invoice data to Google Cloud. Before go-live, a third-party audit must review the database. Auditors need tightly scoped, **read-only** access—no write or admin permissions. You’ll use **Google Cloud IAM** to:

1. Create a **custom role** with least-privilege permissions to view Firebase Realtime Database resources.
2. **Grant** that role to a specific audit user.
3. **Verify** the assignment using **Policy Analyzer**.

This project mirrors a real security workflow for controlled, auditable access.

---

## Project Description


## 1) Sign in to Google Cloud Console 

---

## 2) Create a Custom IAM Role (Least Privilege)

**Goal:** A read-only role for audit viewing of Firebase Realtime Database.

1. Go to **Navigation menu (☰) → IAM & Admin → Roles**.
2. Click **+ Create Role**.
3. Fill in:

   * **Title:** `Audit Team Reviewer`
   * **Description:** `Custom role, allowing the audit team to conduct its review activities. This role grants read-only access to Firebase database resources.`
   * **ID:** `CustomRole`
   * **Role launch stage:** `General Availability`
4. Click **+ Add permissions**.
5. In **Filter permissions by role**, type **Firebase Realtime**.
6. Select **Firebase Realtime Database Viewer**. Click **OK**.
7. In the permissions list, ensure the following are included:

   * `firebase.clients.list`
   * `firebasedatabase.instances.list`
8. Click **Add**, then **Create**.

**Checkpoint:** The `Audit Team Reviewer` role appears in the Roles list.

---

## 3) Grant the Custom Role to the Audit User

**Goal:** Assign the new role to **Username 2** (from Lab Details).

1. Go to **Navigation menu (☰) → IAM & Admin → IAM**.
2. On **View by principals**, click **Grant access**.
3. In **New principals**, paste **Username 2**.
4. In **Select a role** → **Custom** → choose **Audit Team Reviewer**.
5. Click **Save**.

**Checkpoint:** The principal (Username 2) now shows the **Audit Team Reviewer** role.

---

## 4) Verify Role Assignment with Policy Analyzer

**Goal:** Confirm the user has the correct custom role.

1. Go to **Navigation menu (☰) → IAM & Admin → Policy Analyzer**.
2. In **Analyze policies**, click **Create custom query** (Custom Query tile).
3. Under **Set the query parameters**, set **Parameter 1 → Principal**.
4. Paste **Username 2** into the **Principal** field → **Continue**.
5. Under **Advanced options for query results**, select **List resources within resource(s) matching your query**.
6. Click **Analyze → Run query**.

**Expected Result:** Shows **Audit Team Reviewer** granted to the user.
(If a multiple-choice check is asked later, the correct choice is **Audit Team Reviewer**.)

---

# Project Conclussion

You implemented least-privilege access using Google Cloud IAM by:

* Creating a **custom role** tailored for read-only Firebase Realtime Database access,
* **Granting** it to a specific auditor user, and
* **Verifying** the assignment with **Policy Analyzer**.

This pattern is foundational for securing production environments: explicitly grant only what is required, to the right principals, and validate it.

---

# Project Images

Use the following screenshot plan for documentation/evidence:

1. **Roles List (After Creation)**

   * Caption: *Custom role “Audit Team Reviewer” visible in Roles list.*
   * Where: IAM & Admin → Roles.

2. **Create Role Dialog (Filled)**

   * Caption: *Title, Description, ID, and GA launch stage configured.*

3. **Add Permissions Dialog**

   * Caption: *Firebase Realtime Database Viewer selected; extra list permissions added.*

4. **Grant Access Dialog**

   * Caption: *Username 2 added; role “Audit Team Reviewer (Custom)” selected.*

5. **Policy Analyzer Results**

   * Caption: *Query showing “Audit Team Reviewer” granted to Username 2.*

*(Redact usernames if needed in public docs.)*

---

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  
