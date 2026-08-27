<div align="center">

<img src="./assets/adham-profile-framed.png" alt="Adham Elsayed" width="280" />

<img src="./assets/identity-intro.svg" alt="Adham Elsayed — AI Engineer" width="100%" />

<br/>

[![Portfolio](https://img.shields.io/badge/PORTFOLIO-7C3AED?style=for-the-badge&logo=githubpages&logoColor=white)](https://adhamelsayedai.github.io/)
[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/adham-elsayed-)
[![GitHub](https://img.shields.io/badge/GITHUB-24292F?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AdhamElsayedAI)
[![Résumé](https://img.shields.io/badge/RÉSUMÉ-16A34A?style=for-the-badge&logo=readme&logoColor=white)](https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf)

<sub>Computer Vision · Edge AI · RAG / LLM Systems · Model Evaluation</sub>

</div>

---

## 🧭 About Me

> *Build the model → measure the behavior → connect the architecture → ship the system.*

I'm an **AI Engineer** focused on turning models into complete, inspectable systems. My work spans **computer vision, edge deployment, RAG / LLM engineering, model evaluation, APIs, data pipelines, and intelligent applications**.

```python
class AdhamElsayed:
    role = "AI Engineer"
    location = "Egypt"

    focus = [
        "Computer Vision",
        "Edge AI",
        "RAG / LLM Systems",
        "Model Evaluation",
        "Intelligent Applications",
    ]

    systems = {
        "Smart Basket": "edge vision + synchronized retail state",
        "MedFlow": "evidence-grounded RAG + safety validation",
        "Code AI Proctor": "visual inference + auditable exam workflow",
    }

    engineering_loop = "Data → Model → Evaluate → Serve → Product → Iterate"
```

<p align="center">
  <a href="#-featured-systems"><b>Featured Systems</b></a> ·
  <a href="#-core-skills"><b>Core Skills</b></a> ·
  <a href="#-tech-stack"><b>Tech Stack</b></a> ·
  <a href="#-evaluation--evidence"><b>Evidence</b></a> ·
  <a href="#-connect-with-me"><b>Contact</b></a>
</p>

---

# 🔥 Featured Systems

## 👁️ 1. Smart Basket — Edge AI Retail System

Real-time retail product recognition running on **Raspberry Pi 5**, connected to basket-state logic, Firebase synchronization, and a Flutter application.

| | |
|---|---|
| **Repository** | [`Smart-Basket`](https://github.com/AdhamElsayedAI/Smart-Basket) |
| **Stack** | `YOLO` · `OpenCV` · `ONNX Runtime` · `Raspberry Pi 5` · `Firebase` · `Flutter` |
| **Capability** | Edge product detection + stabilized basket state + mobile synchronization |
| **Validation** | `mAP@0.5 = 96.89%` · `mAP@0.5:0.95 = 84.79%` |

### 🏗️ System Architecture

```mermaid
flowchart LR
    CAM[Pi Camera] --> PRE[OpenCV preprocessing]
    PRE --> YOLO[YOLO detector]
    YOLO --> EDGE[ONNX Runtime on Raspberry Pi 5]
    EDGE --> STATE[Basket state tracker]
    STATE -->|state changed| FB[(Firebase)]
    FB --> APP[Flutter application]
    EDGE -. runtime telemetry .-> MON[Runtime monitor]
```

**Architecture notes**

- Camera frames are prepared before inference with OpenCV.
- ONNX Runtime moves inference onto Raspberry Pi 5 instead of depending on a cloud model endpoint.
- Basket-state confirmation / hold behavior reduces unstable product-state changes.
- Firebase updates are written when state changes rather than continuously rewriting identical state.
- Flutter consumes the synchronized basket state at the application layer.

[**Inspect Smart Basket →**](https://github.com/AdhamElsayedAI/Smart-Basket)

---

## 🩺 2. MedFlow — Evidence-Grounded Clinical RAG

A thyroid-focused clinical AI prototype where **retrieval, evidence sufficiency, generation, citation resolution, claim validation, numeric safety, and final policy** are separate system layers.

| | |
|---|---|
| **Repository** | [`Medflow`](https://github.com/AdhamElsayedAI/Medflow) |
| **Stack** | `FastAPI` · `BGE` · `ChromaDB` · `BM25` · `RRF` · `Groq / GPT-OSS` |
| **Capability** | Evidence-grounded answers with traceable citations and explicit safety routing |
| **Retrieval** | `Precision@4 = 53.12%` · `Hit@4 = 87.50%` · `MRR ≈ 0.7031` |

### 🏗️ Runtime Architecture

```mermaid
flowchart TB
    U[User] --> UI[MedFlow web UI]
    UI --> API[FastAPI backend]
    API --> GUARD[Input guardrail]
    GUARD --> RISK{Risk class}

    RISK -->|refuse / redirect| SAFE[Safe redirect]
    RISK -->|allowed / caution| RET[Retrieval layer]

    subgraph Retrieval
      DENSE[Dense retrieval: BGE + ChromaDB]
      SPARSE[Sparse retrieval: BM25]
      FUSION[Reciprocal Rank Fusion]
      DENSE --> FUSION
      SPARSE --> FUSION
    end

    RET --> DENSE
    RET --> SPARSE
    FUSION --> GATE{Evidence sufficiency gate}
    GATE -->|block| ABSTAIN[Abstain]
    GATE -->|pass / downgrade| PACK[Evidence packaging E1..E4]
    PACK --> LLM[Grounded LLM]

    LLM --> CITE[Citation engine]
    LLM --> CLAIM[Claim validator]
    LLM --> NUM[Numeric / dosage validator]

    CITE --> POLICY{Final safety policy}
    CLAIM --> POLICY
    NUM --> POLICY

    POLICY -->|safe| ANSWER[Answer]
    POLICY -->|caution| CAUTION[Answer with caution]
    POLICY -->|insufficient| ABSTAIN
    POLICY -->|unsafe| SAFE
```

### 📚 Offline Evidence Pipeline

```mermaid
flowchart LR
    PDF[Medical PDFs] --> EXT[Text extraction]
    EXT --> CLEAN[Cleaning]
    CLEAN --> CHUNK[Token-aware chunking]
    CHUNK --> META[Metadata enrichment]
    META --> EMB[BGE embeddings]
    EMB --> DB[(ChromaDB)]
```

**Architecture notes**

- Dense and sparse retrieval remain separate before fusion.
- Evidence sufficiency can stop generation before the LLM is allowed to answer.
- Citation resolution is deterministic and separated from claim support.
- Numbers, units, dosages, thresholds, and durations receive stricter validation.
- The final policy can answer, caution, abstain, or redirect.

> The reported values are **engineering evaluation metrics**, not clinical validation or a medical-accuracy claim.

[**Inspect MedFlow →**](https://github.com/AdhamElsayedAI/Medflow)

---

## 🎥 3. Code AI Proctor — AI Exam Monitoring Platform

A self-hosted exam platform connecting webcam inference to organization management, quizzes, incident persistence, teacher review, grading, and student appeals.

| | |
|---|---|
| **Repository** | [`code-ai-proctor`](https://github.com/AdhamElsayedAI/code-ai-proctor) |
| **Stack** | `YOLO` · `PyTorch` · `FastAPI` · `SQLAlchemy` · `HTML/CSS/JS` |
| **Capability** | Local visual inference connected to an auditable exam workflow |
| **AI task** | Binary classification: `cheating` vs `normal` |

### 🏗️ Runtime Architecture

```mermaid
flowchart LR
    CAM[Browser webcam] --> FRAME[Canvas snapshot]
    FRAME --> API[FastAPI /api/predict]
    API --> CROP[Center crop]
    CROP --> YOLO[YOLO classifier]
    YOLO --> TEMP[Temporal logic]
    TEMP -->|normal| CONT[Continue exam]
    TEMP -->|confirmed alert| INCIDENT[Cheating incident]
    INCIDENT --> DB[(SQLAlchemy database)]
    DB --> TEACH[Teacher review]
    TEACH --> GRADE[Grades / CSV export]
    DB --> APPEAL[Student appeal]
```

### 🧩 Platform Workflow

```mermaid
flowchart TD
    ORG[Organization] --> ACC[Teacher / student accounts]
    ACC --> CLASS[Teacher creates class]
    CLASS --> QUIZ[Teacher creates quiz]
    QUIZ --> JOIN[Student joins class]
    JOIN --> ATTEMPT[Quiz attempt]
    ATTEMPT --> PROCTOR[Live AI proctoring]
    PROCTOR --> REVIEW[Incident review]
    REVIEW --> RESULT[Grade / appeal workflow]
```

**Architecture notes**

- YOLO inference runs locally with CUDA when available and CPU fallback otherwise.
- Webcam frames are center-cropped before classification to avoid aspect-ratio distortion.
- Batch probability and streak logic reduce single-frame instability.
- Confirmed incidents are attached to the active quiz attempt and persisted for review.
- Teacher notifications, acknowledgement, grading, CSV export, and student appeals extend the system beyond inference.

[**Inspect Code AI Proctor →**](https://github.com/AdhamElsayedAI/code-ai-proctor)

---

# 📊 Data / Machine Learning

## 4. Telco Customer Churn — PySpark ML

Big-data style churn analysis and binary classification using Spark DataFrames and MLlib.

| | |
|---|---|
| **Repository** | [`Telco-Customer-Churn-Project`](https://github.com/AdhamElsayedAI/Telco-Customer-Churn-Project) |
| **Stack** | `PySpark` · `Spark DataFrames` · `MLlib` · `Google Colab` |
| **Task** | Predict whether a telecom customer will churn |
| **Model** | `Logistic Regression` |

```mermaid
flowchart LR
    CSV[Telco churn CSV] --> SPARK[Spark DataFrame]
    SPARK --> EDA[Analysis]
    EDA --> CAT[Categorical columns]
    CAT --> IDX[StringIndexer]
    IDX --> OHE[OneHotEncoder]
    OHE --> FEAT[Feature vector]
    FEAT --> LR[Logistic Regression]
    LR --> EVAL[Accuracy · F1 · Precision · Recall · AUC]
    EVAL --> CM[Confusion matrix]
```

[**Inspect Telco Churn →**](https://github.com/AdhamElsayedAI/Telco-Customer-Churn-Project)

---

## 5. Student Performance Analysis

A compact exploratory analysis connecting study behavior, attendance, previous performance, final score, and pass/fail status.

| | |
|---|---|
| **Repository** | [`Student-Performance-Analysis`](https://github.com/AdhamElsayedAI/Student-Performance-Analysis) |
| **Stack** | `Python` · `Pandas` · `Matplotlib` · `Google Colab` |
| **Focus** | Exploratory student-performance analysis and visualization |

```mermaid
flowchart LR
    DATA[Student data] --> DF[Pandas DataFrame]
    DF --> QUALITY[Null checks]
    QUALITY --> STATUS[Derived Pass / Fail]
    STATUS --> STATS[Descriptive statistics]
    STATS --> REL[Hours Studied vs Final Score]
    REL --> VIZ[Matplotlib visuals]
    STATUS --> DIST[Pass / Fail distribution]
    DIST --> VIZ
```

[**Inspect Student Performance Analysis →**](https://github.com/AdhamElsayedAI/Student-Performance-Analysis)

---

# 🚀 Core Skills

<div align="center">

![Artificial Intelligence](https://img.shields.io/badge/ARTIFICIAL_INTELLIGENCE-F97316?style=for-the-badge&logo=tensorflow&logoColor=white)
![Computer Vision](https://img.shields.io/badge/COMPUTER_VISION-2563EB?style=for-the-badge&logo=opencv&logoColor=white)
![Edge AI](https://img.shields.io/badge/EDGE_AI-7C3AED?style=for-the-badge&logo=raspberrypi&logoColor=white)
![Machine Learning](https://img.shields.io/badge/MACHINE_LEARNING-16A34A?style=for-the-badge&logo=scikitlearn&logoColor=white)
![RAG LLM Systems](https://img.shields.io/badge/RAG_%2F_LLM_SYSTEMS-0891B2?style=for-the-badge&logo=huggingface&logoColor=white)
![Model Evaluation](https://img.shields.io/badge/MODEL_EVALUATION-DC2626?style=for-the-badge&logo=pytest&logoColor=white)

</div>

---

# 🛠️ Tech Stack

### Programming

<div align="center">

![Python](https://img.shields.io/badge/PYTHON-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=111827)
![Java](https://img.shields.io/badge/JAVA-EA4335?style=for-the-badge&logo=openjdk&logoColor=white)
![Dart](https://img.shields.io/badge/DART-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-EF6C00?style=for-the-badge&logo=mathworks&logoColor=white)

</div>

### AI · Vision · ML

<div align="center">

![PyTorch](https://img.shields.io/badge/PYTORCH-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TENSORFLOW-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/KERAS-D00000?style=for-the-badge&logo=keras&logoColor=white)
![OpenCV](https://img.shields.io/badge/OPENCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=for-the-badge&logo=onnx&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/SCIKIT--LEARN-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Hugging Face](https://img.shields.io/badge/HUGGING_FACE-FFD21E?style=for-the-badge&logo=huggingface&logoColor=111827)
![MLflow](https://img.shields.io/badge/MLFLOW-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)

</div>

### Edge · Cloud · Applications

<div align="center">

![Raspberry Pi](https://img.shields.io/badge/RASPBERRY_PI-A22846?style=for-the-badge&logo=raspberrypi&logoColor=white)
![Arduino](https://img.shields.io/badge/ARDUINO-00878F?style=for-the-badge&logo=arduino&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=for-the-badge&logo=espressif&logoColor=white)
![Flutter](https://img.shields.io/badge/FLUTTER-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![Firebase](https://img.shields.io/badge/FIREBASE-DD2C00?style=for-the-badge&logo=firebase&logoColor=white)
![FastAPI](https://img.shields.io/badge/FASTAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Azure AI](https://img.shields.io/badge/AZURE_AI-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Supabase](https://img.shields.io/badge/SUPABASE-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white)

</div>

### Data · Backend · DevOps

<div align="center">

![Pandas](https://img.shields.io/badge/PANDAS-150458?style=for-the-badge&logo=pandas&logoColor=white)
![PySpark](https://img.shields.io/badge/PYSPARK-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLITE-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Docker](https://img.shields.io/badge/DOCKER-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/GIT-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GITHUB-181717?style=for-the-badge&logo=github&logoColor=white)
![Linux](https://img.shields.io/badge/LINUX-FCC624?style=for-the-badge&logo=linux&logoColor=111827)
![VS Code](https://img.shields.io/badge/VS_CODE-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white)

</div>

---

# 📐 Engineering Principles

```text
01  Understand the failure mode before adding complexity.
02  Measure behavior before calling a component better.
03  Tie every metric to its exact evaluation context.
04  Separate retrieval, generation, validation, and product workflow.
05  Prefer inspectable architecture over black-box demos.
06  Move notebook → inference → API → product.
```

---

# 📈 Evaluation & Evidence

| Project | Measured / inspectable evidence |
|---|---|
| **Smart Basket** | `mAP@0.5 = 96.89%` · `mAP@0.5:0.95 = 84.79%` |
| **MedFlow** | `Precision@4 = 53.12%` · `Hit@4 = 87.50%` · `MRR ≈ 0.7031` |
| **Code AI Proctor** | Local inference · temporal stabilization · incident persistence · review workflow |
| **Telco Churn** | Accuracy · F1 · Precision · Recall · AUC · Confusion Matrix |
| **Student Performance** | Descriptive statistics · relationship analysis · pass/fail visualization |

---

# 🎓 Background

| | |
|---|---|
| **Education** | B.Sc. Artificial Intelligence Engineering — Mansoura University · Sep 2023 – Expected Feb 2027 |
| **Academic standing** | GPA `3.13 / 4.00` · Grade `B+` |
| **Training** | Digital Egypt Pioneers Initiative — Microsoft AI & Data Science / Machine Learning Engineering · Sep 2025 – Jul 2026 |
| **Location** | Egypt 🇪🇬 |

<details>
<summary><b>📊 GitHub activity</b></summary>
<br/>
<div align="center">
<img height="165" src="https://github-readme-stats.vercel.app/api?username=AdhamElsayedAI&show_icons=true&theme=github_dark&hide_border=true&include_all_commits=true&count_private=false" alt="GitHub stats" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=AdhamElsayedAI&layout=compact&theme=github_dark&hide_border=true" alt="Top languages" />
</div>
</details>

---

# 🎯 Current Focus

- **Computer Vision & Edge AI** — detection / classification, efficient local inference, model-to-device integration.
- **RAG / LLM Systems** — retrieval quality, evidence sufficiency, grounding, citation and claim validation.
- **Evaluation** — measurable behavior, failure modes, and system-level iteration.
- **AI Product Engineering** — model → API → workflow → usable product.

---

# 🤝 Connect With Me

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/adham-elsayed-)
[![GitHub](https://img.shields.io/badge/GITHUB-24292F?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AdhamElsayedAI)
[![Portfolio](https://img.shields.io/badge/PORTFOLIO-7C3AED?style=for-the-badge&logo=githubpages&logoColor=white)](https://adhamelsayedai.github.io/)
[![Email](https://img.shields.io/badge/EMAIL-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:adhamelsayed515@gmail.com)

<br/>

**Adham Elsayed** · AI Engineer · Egypt 🇪🇬

<sub>Build the model · Measure the behavior · Ship the system</sub>

</div>
