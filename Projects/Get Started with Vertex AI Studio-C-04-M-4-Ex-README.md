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

![Get Started with Vertex AI Studio](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Get%20Started%20with%20Vertex%20AI%20Studio-01a.jpg)  

* Created the first prompt titled **“Insurance Risk Summary – Prototype.”**

![Get Started with Vertex AI Studio](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Get%20Started%20with%20Vertex%20AI%20Studio-01b.jpg)  

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

![Get Started with Vertex AI Studio](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Get%20Started%20with%20Vertex%20AI%20Studio-02.jpg)  

---

### **Task 3 – Engineer and Manage Prompts**

* Created **“Insurance Risk Factor Identification”** prompt.
* Tested **System Instructions**, **Temperature**, and **Model variations** using the **Compare** feature.
* Compared:

  * *Concise vs. Detailed outputs*
  * *Flash vs. Pro model behavior*
* Observed how **Gemini 2.5 Pro** produced more reasoning-based, guideline-aligned responses compared to **Gemini 2.5 Flash**.

---

## **Task 4 – Use Multimodal Prompts with Gemini**

I created a prompt titled **“Timetable Image Analysis.”**
In this task, I uploaded the **timetable.png** image from **Cloud Storage** and explored **Gemini’s multimodal capabilities** to analyze visual data along with text instructions.

### **Prompt Instructions**

```
1. Provide a concise title for this image (under 5 words).
2. Describe the image in one or two sentences.
3. Extract all visible text from the image. Present the flight schedule as a clearly formatted list with columns for "Time" and "City".
```

### **Follow-up Prompt**

```
Based on the flight schedule shown in the image, what percentage of the listed flights depart before 11:30 AM? Show your calculation if possible.
```

### **Process and Observations**

* Gemini successfully analyzed the timetable image, extracted readable flight data, and organized it into a clear table.
* It also performed reasoning to calculate the percentage of flights departing before **11:30 AM**, providing step-by-step logic in its response.
* I experimented with **Temperature** settings to observe output variations:

  * At **0.2**, the responses were factual, structured, and concise.
  * At **0.8**, the responses became more descriptive and creative in tone.

### **Outcome**

Through this exercise, I learned how to:

* Combine **text and image inputs** in a single multimodal prompt.
* Extract structured information from visual data.
* Use reasoning-based queries for analytical tasks.
* Adjust **model parameters** (like Temperature) to balance precision and creativity.

This task demonstrated the powerful capabilities of **Gemini in Vertex AI Studio** for multimodal analysis and reasoning.

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
