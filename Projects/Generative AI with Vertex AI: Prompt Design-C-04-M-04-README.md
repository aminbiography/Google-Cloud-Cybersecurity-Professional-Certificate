# Project Title: Generative AI with Vertex AI – Prompt Design

---

## Project Objective

The main objective of this project is to understand and apply **prompt engineering best practices** using **Gemini models within Vertex AI**. The focus is on writing effective prompts that are concise, specific, and task-focused, while also learning techniques to reduce hallucinations and improve the quality of model responses.

---

## Project Description

This project was conducted using **Google Cloud Skills Boost Lab (GSP1151)** in a real cloud environment. The steps included setting up the environment, connecting to **Vertex AI Workbench (JupyterLab)**, loading the **Gemini model**, and experimenting with different prompt engineering techniques.

---

### **Step 1: Environment Setup**

* Logged in to **Google Cloud Console** with temporary lab credentials.
* Verified **Project Info** (name, number, ID).

![Generative AI with Vertex AI – Prompt Design](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Generative%20AI%20with%20Vertex%20AI%20Prompt%20Design-01.jpg)

---

### **Step 2: Vertex AI Workbench Access**

* Navigated to **Vertex AI → Workbench**.
* Opened the **JupyterLab instance** (`vertex-ai-jupyterlab`) for coding.


![Generative AI with Vertex AI – Prompt Design](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Generative%20AI%20with%20Vertex%20AI%20Prompt%20Design-02.jpg)

---

### **Step 3: Notebook Initialization**

* Opened the notebook file `intro_prompt_design.ipynb`.
* Configured environment variables and client setup.

```python
import os
PROJECT_ID = "<your-project-id>"   # anonymized
LOCATION = "us-central1"
client = genai.Client(vertexai=True, project=PROJECT_ID, location=LOCATION)
```

![Generative AI with Vertex AI – Prompt Design](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Generative%20AI%20with%20Vertex%20AI%20Prompt%20Design-03.jpg)

---

### **Step 4: Load Gemini Model**

* Selected the **Gemini 2.5 Flash model** for testing.

```python
MODEL_ID = "gemini-2.5-flash"
```

---

### **Step 5: Apply Prompt Engineering Best Practices**

* Explored and tested prompt design strategies:

  * **Be Concise** → Short and direct prompts.
  * **Be Specific & Well-Defined** → Clear, unambiguous instructions.
  * **One Task at a Time** → Prevent multi-task confusion.
  * **Include Examples** → Used few-shot prompts to improve accuracy.

![Generative AI with Vertex AI – Prompt Design](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Generative%20AI%20with%20Vertex%20AI%20Prompt%20Design-03.jpg)

---

### **Step 6: Reduce Output Variability**

* Used **system instructions** as guardrails to reduce irrelevant outputs.
* Converted **generative tasks into classification tasks** to ensure predictable responses.

---

### **Step 7: Improve Response Quality**

* Added **representative examples** to guide the LLM’s behavior.
* Observed significant improvements in model response accuracy and reliability.

---

## Project Conclusion

Through this lab, the following outcomes were achieved:

* Practical experience with **Gemini models on Vertex AI**.
* Application of **prompt design principles** for better outputs.
* Reduced hallucinations using **system prompts and classification framing**.
* Improved LLM reliability with **few-shot examples**.

This project reinforced the importance of **clear, concise, and structured prompts** in real-world generative AI applications.

---

## Project URL
***Google-Cloud***: [Generative AI with Vertex AI: Prompt Design – Google Cloud Skills Boost (GSP1151)](https://www.cloudskillsboost.google/focuses/86501?parent=catalog&utm_source=endlab&utm_campaign=nextlab&utm_medium=email)

---


## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)
- **Contributor**: **Vertex AI Team** – Workbench and SDK
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions
- **Technologies**: **Google DeepMind** – Gemini AI Models
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  
---
