# **Project Title:** **Get Started with Vertex AI Studio**

---

## **Project Objective:**

The objective of this project is to explore and demonstrate the core capabilities of **Vertex AI Studio** by building, refining, and deploying generative AI applications.
Through a hands-on insurance use case, the project focuses on **designing, engineering, and evaluating prompts** that help insurance professionals analyze client data, identify risk factors, and generate summaries efficiently.

By the end of this project, you will have:

* Created and deployed a functional **Generative AI prototype**.
* Experimented with **prompt engineering** and **model configuration**.
* Used **Compare**, **Multimodal**, and **Media Generation** features of Vertex AI Studio.

---

## **Project Steps:**

### **Task 1 – Create Applications from Prompts**

* Accessed **Vertex AI Studio** in the Google Cloud Console.
* Created the first prompt titled **“Insurance Risk Summary – Prototype.”**
* Defined **System Instructions** for an AI assistant supporting underwriting tasks.
* Entered client data (SafeHarbor Warehousing) to test summarization and risk identification.
* Configured **Model: gemini-2.5-flash**, **Temperature: 0.2**, **Region: Global**.
* Deployed the prompt as a **Cloud Run application** and verified functionality via a web interface.

---

### **Task 2 – Design Effective Prompts**

* Created a second prompt, **“Insurance Claim Data Extraction.”**
* Practiced **zero-shot** and **few-shot prompting** to extract structured claim data from unstructured text.
* Explored parameters like **Temperature**, **Top-P**, and **Output Token Limit** to improve accuracy.
* Enhanced prompt structure for consistency and precision.

---

### **Task 3 – Engineer and Manage Prompts**

* Created **“Insurance Risk Factor Identification”** prompt.
* Tested **System Instructions**, **Temperature**, and **Model variations** using the **Compare** feature.
* Compared:

  * *Concise vs. Detailed outputs*
  * *Flash vs. Pro model behavior*
* Observed how **Gemini 2.5 Pro** produced more reasoning-based, guideline-aligned responses compared to **Gemini 2.5 Flash**.

---

### **Task 4 – Use Multimodal Prompts with Gemini**

* Created **“Timetable Image Analysis”** prompt.
* Uploaded an image from Cloud Storage (timetable.png).
* Used **Gemini’s multimodal capability** to:

  * Describe the image.
  * Extract structured flight data.
  * Perform reasoning-based calculations (e.g., flights before 11:30 AM).
* Adjusted **Temperature** to observe variations in style and precision.

---

### **Task 5 – Generate Media in Vertex AI Studio**

* Explored **Imagen** for image generation.
* Created a detailed prompt for generating a **photo-realistic image of a honeybee collecting pollen**.
* Experimented with **inpainting**, **outpainting**, and **SynthID watermark verification**.
* Optionally, used **Chirp** for voice generation — converting text to high-quality AI speech.

---

## **Project Supporting Documents URL:**

**Google Cloud Skills Boost Lab:**
[Get Started with Vertex AI Studio (GSP1154)](https://www.cloudskillsboost.google/focuses/86502?parent=catalog&utm_campaign=nextlab&utm_medium=email&utm_source=endlab)

**Vertex AI Documentation:**
[Vertex AI Studio Overview](https://cloud.google.com/vertex-ai/docs/generative-ai/learn/overview)

**Prompt Design Strategies:**
[Prompt Engineering Guide – Google Cloud](https://cloud.google.com/discover/what-is-prompt-engineering#prompt-engineering-overview)

---

## **Project Conclusion:**

This project successfully demonstrates how **Vertex AI Studio** empowers users to rapidly prototype, test, and deploy generative AI models for real-world scenarios.
Through structured prompt engineering and comparison, the **Insurance Risk Analysis Assistant** was able to identify risk factors, extract structured data, and generate high-quality summaries.

Additionally, by exploring **multimodal inputs** and **AI media generation**, this project highlights Vertex AI Studio’s versatility across text, image, and voice domains.
Overall, the project showcases the power of **Gemini models** and **Google Cloud’s integrated AI platform** in delivering practical business solutions.

---


## **Project Credit:**
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)
- **Platform:** Google Cloud Vertex AI Studio
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions
- **Models Used:** Gemini 2.5 Flash, Gemini 2.5 Pro, Imagen 4, Chirp 3
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  
---
