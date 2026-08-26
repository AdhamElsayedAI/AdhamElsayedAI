<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/hero-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="./assets/hero-light.svg">
    <img src="./assets/hero-dark.svg" alt="Adham Elsayed — AI Engineer working across computer vision, RAG, LLM systems, and intelligent applications" width="100%">
  </picture>
</p>

<p align="center">
  <a href="https://adhamelsayedai.github.io/"><code>PORTFOLIO</code></a>
  &nbsp;·&nbsp;
  <a href="#featured-work"><code>PROJECTS</code></a>
  &nbsp;·&nbsp;
  <a href="https://www.linkedin.com/in/adham-elsayed-"><code>LINKEDIN</code></a>
  &nbsp;·&nbsp;
  <a href="https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf"><code>RÉSUMÉ</code></a>
  &nbsp;·&nbsp;
  <a href="mailto:adhamelsayed515@gmail.com"><code>CONTACT</code></a>
</p>

<img src="./assets/terminal.svg" alt="Adham AI engineering console" width="100%">

## About

I build AI systems end-to-end: from data and model behavior to evaluation, inference, APIs, and usable product workflows. My strongest public work sits across **computer vision at the edge**, **evidence-grounded RAG**, and **AI-backed applications** where failure modes and measurable behavior matter as much as the model itself.

## Engineering approach

<img src="./assets/pipeline.svg" alt="Data to model to evaluation to serving to product to iteration" width="100%">

<a id="featured-work"></a>

## Featured work

### 01 // Smart Basket

<a href="https://github.com/AdhamElsayedAI/Smart-Basket">
  <img src="./assets/project-smart-basket.svg" alt="Smart Basket system architecture" width="100%">
</a>

**Problem.** Turn ordinary retail picking into a connected basket that can recognize products and keep the application state synchronized.

**System.** Pi Camera input feeds a YOLO detector exported to ONNX for CPU inference on Raspberry Pi 5. A basket-state tracker stabilizes detections before writing changes to Firebase; the mobile layer consumes the synchronized state.

**Engineering evidence.**
- Four-class retail detector with OpenCV + ONNX Runtime edge inference.
- Raspberry Pi 5 implementation with Pi Camera support and Firebase writes only when basket state changes.
- Committed validation output reports **`mAP@0.5 = 96.89%`** and **`mAP@0.5:0.95 = 84.79%`**.

[Inspect Smart Basket →](https://github.com/AdhamElsayedAI/Smart-Basket)

---

### 02 // MedFlow

<a href="https://github.com/AdhamElsayedAI/Medflow">
  <img src="./assets/project-medflow.svg" alt="MedFlow retrieval, grounding, validation, and safety architecture" width="100%">
</a>

**Problem.** A fluent answer is not enough in a clinical RAG system; retrieved evidence, claims, citations, and high-risk numeric details need separate checks.

**System.** MedFlow combines dense retrieval with a product hybrid path, an evidence-sufficiency gate, grounded structured generation, deterministic citation resolution, claim support checks, numeric validation, and a final answer/caution/abstain policy.

**Engineering evidence.**
- Frozen retrieval core: BGE-small embeddings, ChromaDB, cosine similarity, `Top-K = 4`.
- Canonical strict passage benchmark: **`Precision@4 = 53.12%`**, **`Hit@4 = 87.50%`**, **`MRR ≈ 0.7031`**.
- Metrics describe the engineering benchmark, **not clinical validation**.
- Team project / public fork; Adham is listed in the repository team.

[Inspect MedFlow →](https://github.com/AdhamElsayedAI/Medflow)

---

### 03 // Code AI Proctor

<a href="https://github.com/AdhamElsayedAI/code-ai-proctor">
  <img src="./assets/project-code-ai-proctor.svg" alt="Code AI Proctor architecture from webcam inference to incident review" width="100%">
</a>

**Problem.** AI proctoring is not only a classifier; it needs a workflow that connects inference to exam state, audit records, teacher review, and student appeals.

**System.** Browser webcam captures are sent to a FastAPI inference endpoint. A local YOLO classifier predicts `cheating` / `normal`, temporal logic reduces single-frame instability, confirmed incidents are persisted, and teachers review the resulting alerts inside the broader exam workflow.

**Engineering evidence.**
- Local YOLO classification with PyTorch/CUDA fallback behavior.
- FastAPI inference and role-based organization / teacher / student workflows.
- SQLAlchemy persistence, incident snapshots, notifications, grade export, and appeal flow.

[Inspect Code AI Proctor →](https://github.com/AdhamElsayedAI/code-ai-proctor)

---

## Technical stack

<img src="./assets/stack.svg" alt="Verified technologies grouped by engineering function" width="100%">

The stack is organized by **what each technology does in a system**, not by self-rated skill levels.

## System context

- **B.Sc. Artificial Intelligence Engineering** — Mansoura University.
- **Machine Learning Engineering Trainee** — Digital Egypt Pioneers Initiative, Microsoft AI & Data Science track.

## Current signal

<img src="./assets/focus.svg" alt="Current AI engineering focus areas" width="100%">

Additional public data work: [Telco Customer Churn with PySpark ML](https://github.com/AdhamElsayedAI/Telco-Customer-Churn-Project) · [Student Performance Analysis](https://github.com/AdhamElsayedAI/Student-Performance-Analysis)

## Open channel

<p align="center">
  <a href="https://adhamelsayedai.github.io/">Portfolio</a>
  &nbsp;·&nbsp;
  <a href="https://www.linkedin.com/in/adham-elsayed-">LinkedIn</a>
  &nbsp;·&nbsp;
  <a href="https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf">Résumé</a>
  &nbsp;·&nbsp;
  <a href="mailto:adhamelsayed515@gmail.com">Email</a>
</p>

<img src="./assets/footer.svg" alt="Build, evaluate, ship, iterate — Adham Elsayed" width="100%">
