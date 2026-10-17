# Adham Elsayed

**AI Engineer** · Generative AI, retrieval systems & computer vision

I build applied AI systems, from data and model behavior to evaluation, APIs, and the workflows people actually use. Most of my work is around **evidence-grounded LLMs**, **computer vision**, and **getting models to run outside a notebook**.

AI Engineering student at **Mansoura University**, Egypt.

[Portfolio](https://adhamelsayedai.github.io/) · [Résumé](https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf) · [LinkedIn](https://www.linkedin.com/in/adham-elsayed-/) · [Email](mailto:adhamelsayed515@gmail.com)

<picture>
  <source media="(prefers-color-scheme: light)" srcset="./assets/focus-light.svg" />
  <img src="./assets/focus-dark.svg" width="620" alt="Current focus: retrieval evaluation, computer vision inference and AI product engineering" />
</picture>

### What I work on

- **LLMs and retrieval:** hybrid search, embeddings, reranking, grounding, citation checks, evaluation and safe fallback behavior.
- **Computer vision:** YOLO-based detection and classification, OpenCV pipelines, ONNX inference and edge devices.
- **AI software:** Python services, FastAPI, SQL, testing and integration with web applications.

### Selected projects

**[MedFlow](https://adhamelsayedai.github.io/#projects)** — Evidence-grounded clinical RAG

A team-built clinical AI prototype that retrieves supporting material, evaluates evidence sufficiency and validates citations before returning a response. My focus has been the retrieval and evaluation side, including safety-aware response states.

`Hybrid retrieval · RAG evaluation · Python · FastAPI`

**[AttendanceOS](https://github.com/AdhamElsayedAI/Smart-Attendance-System)** — University attendance

A local, supervised exam-attendance workflow with a React operator interface, FastAPI service, face matching, blink checks and exam-specific SQLite records.

`React · TypeScript · FastAPI · OpenCV · dlib`

**[Smart Basket](https://github.com/AdhamElsayedAI/Smart-Basket)** — Vision on edge hardware

An object-detection pipeline for four grocery product categories, with ONNX Runtime inference, a Raspberry Pi camera path and optional Firebase basket-state updates.

`YOLO · ONNX Runtime · Raspberry Pi · Firebase`

**[Code AI Proctor](https://github.com/AdhamElsayedAI/code-ai-proctor)** — Assessment and review platform

A browser-based quiz platform with FastAPI endpoints, image-classification alerts for teacher review and Gemini-assisted feedback using course PDFs. Model alerts are review signals, not proof of misconduct.

`PyTorch · YOLO classification · FastAPI · SQLAlchemy · Gemini`

<details>
<summary>Evaluation notes</summary>

MedFlow's internal **16-question retrieval benchmark** reported **Hit@4 of 87.50%** and **MRR of 0.7031**. A separate **seven-case grounding check** reported valid citation IDs across those cases. These results describe limited engineering tests, not clinical accuracy or deployment readiness.

</details>

### Tools I use

**Language & backend:** Python, TypeScript, FastAPI, SQL, React

**ML & vision:** PyTorch, OpenCV, Ultralytics YOLO, NumPy, ONNX Runtime

**Retrieval & systems:** BM25, embeddings, ChromaDB, Docker, Git, Firebase

### How I approach engineering

Start with a baseline. Decide what to measure. Look closely at failure cases. Improve the evidence or model path, then make the system usable and test it again.

I try to keep a clear boundary between **something that works in a demo** and **something that's actually been validated**.

---

[**Explore my work**](https://adhamelsayedai.github.io/) · [**View my CV**](https://adhamelsayedai.github.io/Adham_Elsayed_CV.pdf) · [**Get in touch**](mailto:adhamelsayed515@gmail.com)
