<!-- ═══════════════════════════════════════════════════════════════════════════
     ADHAM ELSAYED — GitHub Profile README · 2026 Edition
═══════════════════════════════════════════════════════════════════════════════ -->

<div align="center">

<a href="https://github.com/AdhamElsayedAI">
  <img src="./assets/identity-intro.svg" alt="Adham Elsayed — AI Engineer; animated identity with portrait, depth layers, and custom name reveal" width="100%"/>
</a>

<br/>

<a href="https://adhamelsayedai.github.io/"><img src="./assets/portfolio-link.svg" alt="Portfolio" width="19%"/></a>
<a href="https://www.linkedin.com/in/adham-elsayed-"><img src="./assets/linkedin-link.svg" alt="LinkedIn" width="19%"/></a>
<a href="https://github.com/AdhamElsayedAI?tab=repositories"><img src="./assets/github-link.svg" alt="Public repositories" width="19%"/></a>
<a href="https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf"><img src="./assets/resume-link.svg" alt="Resume" width="19%"/></a>
<a href="mailto:adhamelsayed515@gmail.com"><img src="./assets/mail-link.svg" alt="Contact" width="19%"/></a>

<img src="./assets/entry-signal.svg" alt="Animated AI engineering signal from perception through retrieval and evaluation to serving and product" width="100%"/>

<sub><b>AI ENGINEER</b> · Computer Vision · RAG / LLM Systems · Edge AI · Evaluation · Intelligent Applications</sub>

</div>

<br/>

## 🧭 About Me

> *"Build the model → measure the behavior → connect the architecture → ship the system."*

I'm an **AI Engineer** building end-to-end intelligent systems across **computer vision**, **edge AI**, **RAG / LLM engineering**, **model evaluation**, and **AI-backed applications**. I care about the full path from model behavior to production workflow — not just notebook results.

```python
class AdhamElsayed:
    name     = "Adham Elsayed"
    role     = "AI Engineer"
    location = "Egypt 🇪🇬"

    expertise = {
        "core": [
            "Computer Vision",
            "RAG / LLM Systems",
            "Model Evaluation",
            "Edge AI",
            "Intelligent Applications",
        ],
        "stack": [
            "Python", "PyTorch", "YOLO", "OpenCV", "ONNX Runtime",
            "FastAPI", "ChromaDB", "Firebase", "SQLAlchemy", "PySpark"
        ],
    }

    current_systems = [
        "🛒 Smart Basket — edge computer vision + synchronized retail state",
        "🩺 MedFlow — evidence-grounded RAG + safety validation",
        "🎥 Code AI Proctor — visual inference + auditable exam workflow",
    ]

    engineering_loop = "Data → Model → Evaluate → Serve → Product → Iterate"
    philosophy       = "Models are components. The system is the product."

    def say_hi(self):
        print("Thanks for visiting — inspect the architecture, not just the headline.")
```

<br/>

## 📌 Quick Navigation

<div align="center">

| | Section | Jump |
|:---:|:---|:---|
| 🔥 | **Featured Systems** | [Smart Basket](#-1-smart-basket--edge-ai-retail-system) · [MedFlow](#-2-medflow--evidence-grounded-clinical-rag) · [Code AI Proctor](#-3-code-ai-proctor--ai-exam-monitoring-platform) |
| 📊 | **Data / ML Projects** | [Telco Churn](#-4-telco-customer-churn--pyspark-ml) · [Student Performance](#-5-student-performance-analysis) |
| 🧠 | **Technical Skills** | [AI / ML](#-core-ai--ml) · [Vision](#-computer-vision--edge-ai) · [RAG](#-rag--llm-engineering) · [Backend](#-backend--data-systems) |
| 📈 | **Evidence** | [Evaluation](#-evaluation--evidence) · [GitHub Stats](#-github-stats) |
| 🎯 | **Now** | [Current Focus](#-current-focus) |

</div>

<br/>

---

# 🔥 Featured Systems

---

## 👁️ 1. Smart Basket — *Edge AI Retail System*

> **Real-time retail product recognition** running on Raspberry Pi 5, connected to basket-state logic, Firebase synchronization, and a Flutter application.

<table>
<tr><td><b>🔗 Repository</b></td><td><a href="https://github.com/AdhamElsayedAI/Smart-Basket"><code>Smart-Basket</code></a></td></tr>
<tr><td><b>📦 Stack</b></td><td><code>YOLO</code> · <code>OpenCV</code> · <code>ONNX Runtime</code> · <code>Raspberry Pi 5</code> · <code>Firebase</code> · <code>Flutter</code></td></tr>
<tr><td><b>🎯 Capability</b></td><td>Edge product detection + stabilized basket state + mobile synchronization</td></tr>
<tr><td><b>📊 Validation</b></td><td><code>mAP@0.5 = 96.89%</code> · <code>mAP@0.5:0.95 = 84.79%</code></td></tr>
</table>

### 🏗️ System Architecture

```mermaid
flowchart LR
    CAM["📷 Pi Camera\nLive Frames"] --> PRE["🧹 OpenCV\nPreprocessing"]
    PRE --> YOLO["🧠 YOLO Detector\n4 Product Classes"]
    YOLO --> EDGE["⚡ ONNX Runtime\nRaspberry Pi 5"]
    EDGE --> STATE["🛒 BasketStateTracker\nConfirm / Hold Logic"]
    STATE -->|"state changed"| FB[("☁️ Firebase\nRealtime Database")]
    FB --> APP["📱 Flutter App\nBasket UI"]
    EDGE -.->|"FPS / detections"| MON["📊 Runtime Monitor"]
```

**Architecture highlights**

- 📷 Camera frames are prepared with OpenCV before inference.
- ⚡ ONNX Runtime moves inference onto Raspberry Pi 5 rather than depending on a cloud model endpoint.
- 🧠 Basket-state confirmation / hold behavior reduces unstable product-state changes.
- ☁️ Firebase updates are pushed when state changes instead of continuously rewriting identical state.
- 📱 Flutter consumes the synchronized state at the application layer.

[**→ Inspect Smart Basket**](https://github.com/AdhamElsayedAI/Smart-Basket)

---

## 🩺 2. MedFlow — *Evidence-Grounded Clinical RAG*

> A thyroid-focused clinical AI prototype where **retrieval, evidence sufficiency, generation, citation resolution, claim validation, numeric safety, and final policy are separate system layers**.

<table>
<tr><td><b>🔗 Repository</b></td><td><a href="https://github.com/AdhamElsayedAI/Medflow"><code>Medflow</code></a></td></tr>
<tr><td><b>📦 Stack</b></td><td><code>FastAPI</code> · <code>BGE</code> · <code>ChromaDB</code> · <code>BM25</code> · <code>RRF</code> · <code>Groq / GPT-OSS</code></td></tr>
<tr><td><b>🎯 Capability</b></td><td>Evidence-grounded answers with traceable citations and explicit safety routing</td></tr>
<tr><td><b>📊 Retrieval</b></td><td><code>Precision@4 = 53.12%</code> · <code>Hit@4 = 87.50%</code> · <code>MRR ≈ 0.7031</code></td></tr>
</table>

### 🏗️ High-Level Architecture

```mermaid
flowchart TB
    U["👤 User / Clinician"] --> UI["🖥️ MedFlow Web UI"]
    UI --> API["⚙️ FastAPI Backend"]
    API --> GUARD["🛡️ Input Guardrail"]
    GUARD --> RISK{"Risk Class"}
    RISK -->|"REFUSE / REDIRECT"| SAFE["↩️ Safe Redirect"]
    RISK -->|"ALLOWED / CAUTION"| RET["🔎 Retrieval Layer"]

    subgraph Retrieval
      DENSE["Dense Retrieval\nBGE + ChromaDB"]
      SPARSE["Sparse Retrieval\nBM25"]
      FUSION["Reciprocal Rank Fusion\nRRF"]
      DENSE --> FUSION
      SPARSE --> FUSION
    end

    RET --> DENSE
    RET --> SPARSE
    FUSION --> GATE{"🚦 Evidence\nSufficiency Gate"}
    GATE -->|"BLOCK"| ABSTAIN["⛔ Abstain"]
    GATE -->|"PASS / DOWNGRADE"| PACK["📦 Evidence Packaging\nE1..E4"]
    PACK --> LLM["🧠 Grounded LLM\nStructured Output"]
    LLM --> CITE["🧾 Citation Engine"]
    LLM --> CLAIM["✅ Claim Validator"]
    LLM --> NUM["🔢 Numeric / Dosage Validator"]
    CITE --> POLICY{"🛡️ Final Safety Policy"}
    CLAIM --> POLICY
    NUM --> POLICY
    POLICY -->|"Safe"| ANSWER["✅ Answer"]
    POLICY -->|"Caution"| CAUTION["⚠️ Answer With Caution"]
    POLICY -->|"Insufficient"| ABSTAIN
    POLICY -->|"Unsafe"| SAFE
```

### 📚 Offline Evidence Pipeline

```mermaid
flowchart LR
    PDF["📄 Medical PDFs"] --> EXT["Text Extraction"]
    EXT --> CLEAN["Cleaning"]
    CLEAN --> CHUNK["Token-Aware Chunking"]
    CHUNK --> META["Metadata Enrichment"]
    META --> EMB["BGE Embeddings"]
    EMB --> DB[("ChromaDB")]
```

**Architecture highlights**

- 🔎 Dense and sparse retrieval are modeled separately before fusion.
- 🚦 Evidence sufficiency can stop generation before the LLM is allowed to answer.
- 🧾 Citation resolution is deterministic and separate from claim support.
- 🔢 Numbers, units, dosages, thresholds, and durations receive stricter validation.
- 🛡️ The final policy can **answer, caution, abstain, or redirect**.

> The reported metrics are **engineering evaluation metrics**, not clinical validation or a medical-accuracy claim.

[**→ Inspect MedFlow**](https://github.com/AdhamElsayedAI/Medflow)

---

## 🎥 3. Code AI Proctor — *AI Exam Monitoring Platform*

> A self-hosted exam platform that connects **webcam inference** to organization management, quizzes, incident persistence, teacher review, grading, and student appeals.

<table>
<tr><td><b>🔗 Repository</b></td><td><a href="https://github.com/AdhamElsayedAI/code-ai-proctor"><code>code-ai-proctor</code></a></td></tr>
<tr><td><b>📦 Stack</b></td><td><code>YOLO</code> · <code>PyTorch</code> · <code>FastAPI</code> · <code>SQLAlchemy</code> · <code>HTML/CSS/JS</code></td></tr>
<tr><td><b>🎯 Capability</b></td><td>Local visual inference connected to an auditable exam workflow</td></tr>
<tr><td><b>🧠 AI Task</b></td><td>Binary classification: <code>cheating</code> vs <code>normal</code></td></tr>
</table>

### 🏗️ Runtime Architecture

```mermaid
flowchart LR
    CAM["📹 Browser Webcam\ngetUserMedia"] --> FRAME["🖼️ Canvas Snapshot"]
    FRAME --> API["⚙️ FastAPI\n/api/predict"]
    API --> CROP["✂️ Center Crop"]
    CROP --> YOLO["🧠 YOLO Classifier\ncheating / normal"]
    YOLO --> TEMP["⏱️ Temporal Logic\nBatch Probability + Streaks"]
    TEMP -->|"normal"| CONT["▶️ Continue Exam"]
    TEMP -->|"confirmed alert"| INCIDENT["🚨 Cheating Incident\nSnapshot + Attempt"]
    INCIDENT --> DB[("🗄️ SQLAlchemy DB")]
    DB --> TEACH["👨‍🏫 Teacher Review\nNotifications + Acknowledge"]
    TEACH --> GRADE["📊 Grades / CSV Export"]
    DB --> APPEAL["📝 Student Appeal"]
```

### 🧩 Platform Workflow

```mermaid
flowchart TD
    ORG["🏢 Organization"] --> ACC["Create Teacher / Student Accounts"]
    ACC --> CLASS["👨‍🏫 Teacher Creates Class"]
    CLASS --> QUIZ["📝 Teacher Creates Quiz"]
    QUIZ --> JOIN["🎓 Student Joins Class"]
    JOIN --> ATTEMPT["⏱️ Quiz Attempt"]
    ATTEMPT --> PROCTOR["🎥 Live AI Proctoring"]
    PROCTOR --> REVIEW["🔍 Incident Review"]
    REVIEW --> RESULT["📊 Grade / Appeal Workflow"]
```

**Architecture highlights**

- 🧠 YOLO inference runs locally with CUDA when available and CPU fallback otherwise.
- ✂️ Webcam frames are center-cropped before classification to avoid aspect-ratio distortion.
- ⏱️ Batch probability and streak logic avoid treating a single unstable frame as a final incident.
- 🚨 Confirmed alerts are tied to the active quiz attempt and stored for review.
- 👨‍🏫 Teacher notifications, incident acknowledgement, grading, CSV export, and student appeals extend the system far beyond inference.

[**→ Inspect Code AI Proctor**](https://github.com/AdhamElsayedAI/code-ai-proctor)

---

# 📊 Data / Machine Learning Projects

---

## 📡 4. Telco Customer Churn — *PySpark ML*

> Big-data style churn analysis and binary classification using **Spark DataFrames + MLlib**.

<table>
<tr><td><b>🔗 Repository</b></td><td><a href="https://github.com/AdhamElsayedAI/Telco-Customer-Churn-Project"><code>Telco-Customer-Churn-Project</code></a></td></tr>
<tr><td><b>📦 Stack</b></td><td><code>PySpark</code> · <code>Spark DataFrames</code> · <code>MLlib</code> · <code>Google Colab</code></td></tr>
<tr><td><b>🎯 Task</b></td><td>Predict whether a telecom customer will churn</td></tr>
<tr><td><b>🧠 Model</b></td><td><code>Logistic Regression</code></td></tr>
</table>

### 🏗️ ML Pipeline Architecture

```mermaid
flowchart LR
    CSV["📄 Telco Churn CSV"] --> SPARK["⚡ Spark DataFrame"]
    SPARK --> EDA["📊 Analysis\ngroupBy · count · avg · filter"]
    EDA --> CAT["🔤 Categorical Columns"]
    CAT --> IDX["StringIndexer"]
    IDX --> OHE["OneHotEncoder"]
    OHE --> FEAT["🧩 Feature Vector"]
    FEAT --> LR["🧠 Logistic Regression"]
    LR --> EVAL["📈 Evaluation\nAccuracy · F1 · Precision · Recall · AUC"]
    EVAL --> CM["🧮 Confusion Matrix"]
```

**Architecture highlights**

- ⚡ Uses Spark DataFrames for aggregation and churn analysis.
- 🔤 String categorical features are converted using `StringIndexer` and `OneHotEncoder`.
- 🧠 Logistic Regression matches the binary churn target.
- 📈 Evaluation covers classification quality through Accuracy, F1, Precision, Recall, AUC, and a confusion matrix.

[**→ Inspect Telco Churn**](https://github.com/AdhamElsayedAI/Telco-Customer-Churn-Project)

---

## 🎓 5. Student Performance Analysis

> A compact exploratory analysis notebook connecting study behavior, attendance, previous performance, final score, and pass/fail status.

<table>
<tr><td><b>🔗 Repository</b></td><td><a href="https://github.com/AdhamElsayedAI/Student-Performance-Analysis"><code>Student-Performance-Analysis</code></a></td></tr>
<tr><td><b>📦 Stack</b></td><td><code>Python</code> · <code>Pandas</code> · <code>Matplotlib</code> · <code>Google Colab</code></td></tr>
<tr><td><b>🎯 Focus</b></td><td>Exploratory student-performance analysis and visualization</td></tr>
</table>

### 🏗️ Analysis Architecture

```mermaid
flowchart LR
    DATA["📚 Student Data\nHours · Attendance · Previous Score · Final Score"] --> DF["🐼 Pandas DataFrame"]
    DF --> QUALITY["🧹 Data Quality\nNull Checks"]
    QUALITY --> STATUS["🏷️ Derived Status\nPass / Fail"]
    STATUS --> STATS["📊 Descriptive Statistics"]
    STATS --> REL["🔎 Relationship Analysis\nHours Studied ↔ Final Score"]
    REL --> VIZ["📈 Matplotlib Visuals"]
    STATUS --> DIST["📊 Pass vs Fail Distribution"]
    DIST --> VIZ
```

**Architecture highlights**

- 🐼 Builds the analysis around a structured Pandas DataFrame.
- 🧹 Explicit null checking precedes the derived analysis.
- 🏷️ Final score is transformed into a `Pass` / `Fail` status for categorical analysis.
- 📊 Descriptive statistics and visual analysis are separated from data preparation.
- 📈 Matplotlib is used for relationship and distribution views.

[**→ Inspect Student Performance Analysis**](https://github.com/AdhamElsayedAI/Student-Performance-Analysis)

---

# 🚀 Technical Skills

## 🧠 Core AI / ML

| Capability | Evidence in public work |
|:---|:---|
| **Model Training & Evaluation** | YOLO validation · retrieval benchmarks · classification evaluation |
| **Deep Learning** | YOLO / PyTorch-based vision systems |
| **Model Optimization** | ONNX export and Raspberry Pi inference |
| **Evaluation-First Development** | mAP · Precision@K · Hit@K · MRR · guardrail / safety tests |
| **Big Data ML** | PySpark DataFrames + MLlib churn pipeline |

---

## 👁️ Computer Vision & Edge AI

`YOLO` · `PyTorch` · `OpenCV` · `ONNX Runtime` · `Raspberry Pi 5` · `Pi Camera`

**Applied in:** Smart Basket · Code AI Proctor

---

## 🔗 RAG / LLM Engineering

`BGE Embeddings` · `ChromaDB` · `BM25` · `RRF` · `Grounded Generation` · `Citation Resolution` · `Claim Validation` · `Numeric Safety` · `Guardrails`

**Applied in:** MedFlow

---

## ⚙️ Backend & Data Systems

`FastAPI` · `REST APIs` · `SQLAlchemy` · `Firebase` · `PySpark` · `Spark MLlib` · `Pandas` · `SQLite / SQL`

---

## 🖥️ Application Layer

`HTML` · `CSS` · `JavaScript` · `Flutter`

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

| Project | Measured / Inspectable Evidence |
|:---|:---|
| **Smart Basket** | `mAP@0.5 = 96.89%` · `mAP@0.5:0.95 = 84.79%` |
| **MedFlow** | `Precision@4 = 53.12%` · `Hit@4 = 87.50%` · `MRR ≈ 0.7031` |
| **Code AI Proctor** | Local inference · temporal stabilization · incident persistence · review workflow |
| **Telco Churn** | Accuracy · F1 · Precision · Recall · AUC · Confusion Matrix |
| **Student Performance** | Descriptive statistics · relationship analysis · pass/fail visualization |

---

# 🎓 Background

| | |
|:---|:---|
| **Education** | B.Sc. Artificial Intelligence Engineering — Mansoura University |
| **Training** | Digital Egypt Pioneers Initiative — Microsoft AI & Data Science / Machine Learning Engineering track |
| **Location** | Egypt 🇪🇬 |

---

# 📊 GitHub Stats

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=AdhamElsayedAI&show_icons=true&theme=github_dark&hide_border=true&include_all_commits=true&count_private=false" alt="Adham Elsayed GitHub stats"/>
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=AdhamElsayedAI&layout=compact&theme=github_dark&hide_border=true" alt="Top languages"/>

<br/>

<img src="https://streak-stats.demolab.com?user=AdhamElsayedAI&theme=github-dark-blue&hide_border=true" alt="GitHub streak"/>

</div>

---

# 🎯 Current Focus

```text
╔══════════════════════════════════════════════════════════════════════════════╗
║                         CURRENT ENGINEERING FOCUS                           ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║  👁️  Computer Vision & Edge AI                                              ║
║      ├── detection / classification systems                                  ║
║      ├── efficient local inference                                           ║
║      └── model → device → application integration                            ║
║                                                                              ║
║  🔗  RAG / LLM Systems                                                       ║
║      ├── retrieval quality and evidence sufficiency                          ║
║      ├── grounding / citation / claim validation                             ║
║      └── safety, abstention, and refusal behavior                            ║
║                                                                              ║
║  📊  Evaluation                                                              ║
║      ├── measurable system behavior                                          ║
║      └── failure-mode driven iteration                                       ║
║                                                                              ║
║  ⚙️  AI Product Engineering                                                  ║
║      └── model → API → workflow → usable product                             ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

<div align="center">

**Adham Elsayed** · AI Engineer · Egypt 🇪🇬  

[Portfolio](https://adhamelsayedai.github.io/) · [LinkedIn](https://www.linkedin.com/in/adham-elsayed-) · [Résumé](https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf) · [Email](mailto:adhamelsayed515@gmail.com)

<br/>

⚡ **Build the model · Measure the behavior · Ship the system**

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:161b22,100:0d1117&height=80&section=footer" width="100%"/>

</div>
