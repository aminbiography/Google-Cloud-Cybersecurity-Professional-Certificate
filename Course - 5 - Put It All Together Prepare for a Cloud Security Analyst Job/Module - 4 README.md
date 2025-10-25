# Generative AI, Large Language Models, and Responsible AI**

## 1. Introduction to Generative AI — *Roger Martinez*

### What is Generative AI

* Generative AI (Gen AI) is a type of artificial intelligence that can **create new content** — text, images, audio, or synthetic data.
* It **learns from existing data** and then generates new data that shares similar patterns or characteristics.

### Artificial Intelligence and Machine Learning

* **AI**: A branch of computer science that creates intelligent systems capable of reasoning, learning, and acting autonomously.
* **Machine Learning (ML)**: A subfield of AI that trains models to learn from data and make predictions without explicit programming.

### Types of Machine Learning

* **Supervised Learning**: Uses labeled data to predict future outcomes (e.g., predicting tips based on bill amount).
* **Unsupervised Learning**: Uses unlabeled data to discover hidden patterns or clusters (e.g., grouping employees by income and tenure).
* **Semi-Supervised Learning**: Combines both labeled and unlabeled data to improve performance.

### Deep Learning

* A subset of ML using **artificial neural networks** inspired by the human brain.
* Processes complex data patterns with many layers of neurons.

### Generative vs. Discriminative Models

* **Discriminative Models**: Classify or predict labels for given data (e.g., “Is this a cat?”).
* **Generative Models**: Learn the data distribution and generate new examples (e.g., creating an image of a dog).

### When is it Generative AI?

* **Not Gen AI** when output is a number, class, or probability.
* **Gen AI** when output is creative content — text, image, audio, or video.

### Foundation Models

* Large models trained on vast data sources that can be adapted for multiple downstream tasks like text, image, or audio generation.
* Examples: **PaLM**, **LaMDA**, **Gemini**.

### Google Cloud Tools for Gen AI

* **Vertex AI Studio**: Explore and customize generative models.
* **Vertex AI Search & Conversation**: Build apps and chatbots with minimal coding.
* **PaLM API + Maker Suite**: Experiment, train, deploy, and monitor LLMs.
* **Gemini**: A multimodal AI model capable of understanding text, code, images, and audio.

---

## 2. Large Language Models (LLMs) — *Megha*

### What are Large Language Models

* LLMs are **large, general-purpose language models** trained on massive datasets and fine-tuned for specific tasks.
* They are a **subset of deep learning** and are closely related to generative AI.

### Key Features of LLMs

1. **Large**:

   * Trained on huge datasets (often petabytes of text).
   * Contain billions of parameters (model’s “memory” and “knowledge”).
2. **General Purpose**:

   * Solve a wide range of common language tasks (translation, summarization, Q&A).
3. **Pre-trained & Fine-tuned**:

   * Pre-trained on general data, then fine-tuned for domain-specific applications (e.g., healthcare, finance).

### Benefits of LLMs

* One model can perform multiple tasks.
* Requires minimal additional data for customization.
* Works in **few-shot** or **zero-shot** learning scenarios.
* Improves performance as data and parameters increase.

### Transformer Architecture

* Uses **encoder-decoder** structure.
* Encoder processes input; decoder generates output.
* Foundation for most modern LLMs like Gemini or LaMDA.

### LLM vs. Traditional ML

| Aspect    | Traditional ML           | LLM Development         |
| --------- | ------------------------ | ----------------------- |
| Expertise | Requires ML experts      | Accessible to anyone    |
| Training  | Needs large labeled data | Uses pre-trained models |
| Process   | Code + data + compute    | Prompt design only      |

### Prompt Design and Engineering

* **Prompt Design**: Creating clear and concise inputs for models to perform tasks effectively.
* **Prompt Engineering**: Advanced version — optimizing prompts for better accuracy using examples or keywords.

### Types of LLMs

1. **Generic Models**: Predict next words (auto-complete).
2. **Instruction-Tuned Models**: Follow user instructions (e.g., summarize, classify).
3. **Dialog-Tuned Models**: Trained for conversational responses (chatbots).
4. **Chain-of-Thought Reasoning**: Model improves accuracy when it explains reasoning before giving an answer.

### Model Tuning Techniques

* **Fine-Tuning**: Retrain all parameters for a new domain (expensive).
* **Parameter-Efficient Tuning (PETM)**: Train only small add-on layers for efficiency.

### Google Cloud Tools for LLMs

* **Vertex AI Studio**: Explore, fine-tune, and deploy models easily.
* **Vertex AI Agent Builder**: Build chatbots and assistants without coding.
* **Gemini**: Multimodal LLM that processes text, images, audio, and code.
* **Model Garden**: Continuously updated hub of foundation models.

---

## 3. Responsible AI — *Manny*

### What is Responsible AI

* The practice of designing, developing, and deploying AI systems **ethically, safely, and fairly**.
* Ensures AI benefits everyone and reduces risks like bias or misuse.

### Why It Matters

* AI mirrors human society — without good practices, it can **replicate or amplify biases**.
* No universal definition exists; each organization defines its own principles.
* Common themes: **Transparency**, **Fairness**, **Accountability**, **Privacy**.

### Google’s Approach to Responsible AI

* Built around **AI for everyone**, **privacy and safety**, and **scientific excellence**.
* Responsibility is **embedded by design** across all Google products and teams.
* AI principles act as a **framework for decision-making** throughout the AI lifecycle.

### Human Role in AI

* Humans design, train, and deploy AI systems — decisions always reflect **human values**.
* Responsibility applies at every stage: from data collection → model training → deployment.
* Ethical consideration is vital to avoid unintended consequences or harm.

### Importance of Ethics

* Responsible AI is not limited to controversial cases.
* Even small or well-intentioned AI projects can lead to ethical problems without safeguards.
* Ethical design = better models + higher trust + long-term success.

### Trust and Process

* **Trust** is essential — losing it can stall or destroy AI projects.
* Google uses **reviews and assessments** to ensure all projects align with its AI principles.
* A trusted process is as important as the final outcome.

### Google’s Three Core AI Principles

1. **Bold Innovation**

   * Build AI that empowers people, drives progress, and solves global challenges.
2. **Responsible Development & Deployment**

   * Apply responsibility throughout the lifecycle — from design to iteration.
3. **Collaborative Progress**

   * Empower others to use AI for collective benefit.

### Core Belief

> **Responsible AI = Successful AI**

Building responsible systems ensures sustainability, fairness, and public trust.

---

