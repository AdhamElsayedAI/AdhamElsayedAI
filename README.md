<div align="center">

<img src="./assets/adham-cutout.webp" alt="Adham Elsayed" width="190" />

<img src="./assets/identity-intro.svg" alt="Adham Elsayed — AI Engineer" width="100%" />

<a href="https://adhamelsayedai.github.io/"><img src="./assets/portfolio-link.svg" alt="Portfolio" width="23.5%" /></a>
<a href="https://www.linkedin.com/in/adham-elsayed-"><img src="./assets/linkedin-link.svg" alt="LinkedIn" width="23.5%" /></a>
<a href="https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf"><img src="./assets/resume-link.svg" alt="Résumé" width="23.5%" /></a>
<a href="mailto:adhamelsayed515@gmail.com"><img src="./assets/mail-link.svg" alt="Contact" width="23.5%" /></a>

<img src="./assets/entry-signal.svg" alt="Perception to retrieval to evaluation to serving to product" width="100%" />

</div>

## About

> *Build the model → measure the behavior → connect the architecture → ship the system.*

I'm an **AI Engineer** working across computer vision, edge AI, RAG / LLM systems, model evaluation, and intelligent applications. My strongest work is built around complete systems: the model is one component, while retrieval, validation, inference, APIs, state, and product workflow determine whether the result is actually useful.

```python
class AdhamElsayed:
    role = "AI Engineer"
    location = "Egypt"

    focus = [
        "Computer Vision",
        "RAG / LLM Systems",
        "Model Evaluation",
        "Edge AI",
        "Intelligent Applications",
    ]

    current_systems = {
        "Smart Basket": "edge vision + synchronized retail state",
        "MedFlow": "evidence-grounded RAG + safety validation",
        "Code AI Proctor": "visual inference + auditable exam workflow",
    }

    engineering_loop = "Data → Model → Evaluate → Serve → Product → Iterate"
```

<p align="center">
  <a href="#featured-systems">Featured Systems</a> ·
  <a href="#data--machine-learning">Data / ML</a> ·
  <a href="#technical-stack">Technical Stack</a> ·
  <a href="#evaluation--evidence">Evidence</a> ·
  <a href="#current-focus">Current Focus</a>
</p>

---

# Featured Systems

## 1. Smart Basket — Edge AI Retail System

Real-time retail product recognition running on Raspberry Pi 5, connected to basket-state logic, Firebase synchronization, and a Flutter application.

| | |
|---|---|
| **Repository** | [`Smart-Basket`](https://github.com/AdhamElsayedAI/Smart-Basket) |
| **Stack** | `YOLO` · `OpenCV` · `ONNX Runtime` · `Raspberry Pi 5` · `Firebase` · `Flutter` |
| **Capability** | Edge product detection + stabilized basket state + mobile synchronization |
| **Validation** | `mAP@0.5 = 96.89%` · `mAP@0.5:0.95 = 84.79%` |

### System architecture

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

[Inspect Smart Basket →](https://github.com/AdhamElsayedAI/Smart-Basket)

---

## 2. MedFlow — Evidence-Grounded Clinical RAG

A thyroid-focused clinical AI prototype where retrieval, evidence sufficiency, generation, citation resolution, claim validation, numeric safety, and final policy are separate system layers.

| | |
|---|---|
| **Repository** | [`Medflow`](https://github.com/AdhamElsayedAI/Medflow) |
| **Stack** | `FastAPI` · `BGE` · `ChromaDB` · `BM25` · `RRF` · `Groq / GPT-OSS` |
| **Capability** | Evidence-grounded answers with traceable citations and explicit safety routing |
| **Retrieval** | `Precision@4 = 53.12%` · `Hit@4 = 87.50%` · `MRR ≈ 0.7031` |

### Runtime architecture

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

### Offline evidence pipeline

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

[Inspect MedFlow →](https://github.com/AdhamElsayedAI/Medflow)

---

## 3. Code AI Proctor — AI Exam Monitoring Platform

A self-hosted exam platform connecting webcam inference to organization management, quizzes, incident persistence, teacher review, grading, and student appeals.

| | |
|---|---|
| **Repository** | [`code-ai-proctor`](https://github.com/AdhamElsayedAI/code-ai-proctor) |
| **Stack** | `YOLO` · `PyTorch` · `FastAPI` · `SQLAlchemy` · `HTML/CSS/JS` |
| **Capability** | Local visual inference connected to an auditable exam workflow |
| **AI task** | Binary classification: `cheating` vs `normal` |

### Runtime architecture

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

### Platform workflow

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

[Inspect Code AI Proctor →](https://github.com/AdhamElsayedAI/code-ai-proctor)

---

# Data / Machine Learning

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

[Inspect Telco Churn →](https://github.com/AdhamElsayedAI/Telco-Customer-Churn-Project)

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

[Inspect Student Performance Analysis →](https://github.com/AdhamElsayedAI/Student-Performance-Analysis)

---

# Technical Stack

### Core AI / ML

`Python` · `PyTorch` · `TensorFlow` · `Scikit-learn` · `YOLO`

### Computer Vision / Edge

`OpenCV` · `ONNX Runtime` · `Raspberry Pi 5` · `Pi Camera`

### RAG / LLM

`BGE Embeddings` · `ChromaDB` · `BM25` · `RRF` · `Grounded Generation` · `Citation Resolution` · `Claim Validation` · `Numeric Safety` · `Guardrails`

### Backend / Data

`FastAPI` · `REST APIs` · `SQLAlchemy` · `Firebase` · `PySpark` · `Spark MLlib` · `Pandas` · `SQLite / SQL`

### Application Layer

`HTML` · `CSS` · `JavaScript` · `Flutter`

---

# Engineering Principles

```text
01  Understand the failure mode before adding complexity.
02  Measure behavior before calling a component better.
03  Tie every metric to its exact evaluation context.
04  Separate retrieval, generation, validation, and product workflow.
05  Prefer inspectable architecture over black-box demos.
06  Move notebook → inference → API → product.
```

---

# Evaluation & Evidence

| Project | Measured / inspectable evidence |
|---|---|
| **Smart Basket** | `mAP@0.5 = 96.89%` · `mAP@0.5:0.95 = 84.79%` |
| **MedFlow** | `Precision@4 = 53.12%` · `Hit@4 = 87.50%` · `MRR ≈ 0.7031` |
| **Code AI Proctor** | Local inference · temporal stabilization · incident persistence · review workflow |
| **Telco Churn** | Accuracy · F1 · Precision · Recall · AUC · Confusion Matrix |
| **Student Performance** | Descriptive statistics · relationship analysis · pass/fail visualization |

---

# Background

| | |
|---|---|
| **Education** | B.Sc. Artificial Intelligence Engineering — Mansoura University |
| **Training** | Digital Egypt Pioneers Initiative — Microsoft AI & Data Science / Machine Learning Engineering track |
| **Location** | Egypt |

<details>
<summary><b>GitHub activity</b></summary>
<br/>
<div align="center">
<img height="165" src="https://github-readme-stats.vercel.app/api?username=AdhamElsayedAI&show_icons=true&theme=github_dark&hide_border=true&include_all_commits=true&count_private=false" alt="GitHub stats" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=AdhamElsayedAI&layout=compact&theme=github_dark&hide_border=true" alt="Top languages" />
</div>
</details>

---

# Current Focus

- **Computer Vision & Edge AI** — detection / classification, efficient local inference, model-to-device integration.
- **RAG / LLM Systems** — retrieval quality, evidence sufficiency, grounding, citation and claim validation.
- **Evaluation** — measurable behavior, failure modes, and system-level iteration.
- **AI Product Engineering** — model → API → workflow → usable product.

---

<div align="center">

**Adham Elsayed** · AI Engineer · Egypt

[Portfolio](https://adhamelsayedai.github.io/) · [LinkedIn](https://www.linkedin.com/in/adham-elsayed-) · [Résumé](https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf) · [Email](mailto:adhamelsayed515@gmail.com)

<sub>Build the model · Measure the behavior · Ship the system</sub>

</div>
