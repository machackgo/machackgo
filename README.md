# Mohammed Mubashir Uddin Faraz

M.S. Artificial Intelligence student at [Worcester Polytechnic Institute](https://www.wpi.edu/) (expected Aug 2027).
I work on AI engineering: LLM evaluation and distillation, retrieval-augmented generation, agentic workflows,
and the infrastructure that makes ML experiments reproducible.

[LinkedIn](https://www.linkedin.com/in/mohammed-mubashir-uddin-faraz-a74675259/) ·
[Hugging Face](https://huggingface.co/MOHDMUBASHIR)

---

## Current work

### [ULTRON](https://github.com/machackgo/ULTRON) — reasoning termination and teacher–student distillation

Research infrastructure for studying whether a smaller Qwen student can learn *when to stop reasoning* from a
larger teacher, so that it closes code tasks instead of over-thinking or truncating.

- **Evaluation harness** — versioned graders (code execution, answer checks, tool selection, reliability),
  deterministic rendering/parsing, frozen evaluation configurations and per-item provenance.
- **Distillation stack** — streamed FP8 teacher scoring, student training arms (supervised baseline vs. two
  distillation variants), termination-aware loss terms, deterministic training with bit-identical resume checks.
- **Experiment controls** — held-out isolation, train/eval leakage screening, pre-registered decision rules and
  independent review before any result is reported.
- **Infrastructure** — Slurm jobs on WPI's Turing cluster (NVIDIA A30), Hugging Face Transformers/PEFT, PyTorch.

Status: evaluation and training infrastructure are built and engineering-validated; the distillation experiments are
in progress and **no distillation outcome is claimed yet**. The Stage 1 evaluation infrastructure is public; the
distillation code was developed in a WPI CS541 group project and will be published after course approval.

`Python` `PyTorch` `Transformers` `PEFT/QLoRA` `Slurm` `Qwen`

### [Resume AI](https://github.com/machackgo/Resume-AI) — evidence-grounded RAG for job applications

A retrieval and generation pipeline that tailors application documents only from verifiable evidence about the
candidate, with a human approving every step that leaves the system.

- **Retrieval** — MiniLM sentence embeddings, structural chunking with exact character offsets, provenance on every
  chunk, semantic / BM25 / hybrid retrieval with reciprocal rank fusion, and requirement decomposition so each part
  of a job description retrieves its own evidence.
- **Grounding** — every generated document goes through a claim validator: banned or disputed claims, numbers that
  do not appear in the evidence, and ongoing work presented as finished all fail validation.
- **Workflow** — job-description matching and an SQLite application tracker whose database triggers refuse a
  submission without the candidate's recorded approval. The system never submits an application by itself.

A synthetic, CPU-only demo and about 300 tests run with `pytest` in a few seconds.

`Python` `sentence-transformers` `RAG` `SQLite` `Qwen` `pytest`

---

## Other projects

| Project | What it is | Stack |
|---|---|---|
| [Boston accident-risk rerouting (Google Cloud)](https://github.com/machackgo/boston-smart-accident-risk-rerouting-google-cloud) | Four-person team project: accident-risk model on MassDOT crash data (2015–2024) served as an API and used to rank alternative routes | FastAPI, Cloud Run, Cloud SQL, scikit-learn |
| [Boston rerouting — MLOps edition](https://github.com/machackgo/boston-smart-accident-risk-rerouting-mlops) | Containerised serving and deployment variant of the same system | Docker, FastAPI |
| [CS3 QA monitoring](https://github.com/machackgo/cs3-qa-monitoring) | Prometheus/Grafana monitoring for two QA services ([API-based](https://github.com/machackgo/qa-api), [local model](https://github.com/machackgo/qa-local)) — MLOps coursework | Docker, Prometheus, Grafana, GitHub Actions |
| [Object detection app](https://github.com/machackgo/cs1-object-detection) | Gradio app for DETR ResNet-50 inference, deployed as a [Hugging Face Space](https://huggingface.co/spaces/MOHDMUBASHIR/cs1-object-detection) | Gradio, Hugging Face |
| [Posture detection](https://github.com/machackgo/Posture_Detection) | Webcam posture classification from MediaPipe pose landmarks | OpenCV, MediaPipe, scikit-learn |
| [Stroke prediction](https://github.com/machackgo/Stroke-Prediction-Model-) | Decision-tree risk model with evaluation (ROC/PR) and a web front end | scikit-learn, TypeScript |
| [FightingICE CNN agent](https://github.com/machackgo/Fighting_ICE_Using_CNN) | CNN-based agent for the FightingICE game, trained from visual game state | Python, TensorFlow/Keras |
| [CPA completion forecaster](https://github.com/machackgo/Hackathon_CPA_Forecaster) | Hackathon build: random-forest classifier behind a Next.js app | scikit-learn, Next.js |
| [Rescue-mission LoRA adapter](https://huggingface.co/MOHDMUBASHIR/team15-qwen3.5-2b-rescue-mission-lora) | Code Metal Forge Hackathon (Nov 2026), team adapter: Qwen3.5-2B LoRA for advisory mission-step generation | PEFT, Qwen |

---

## Skills

- **ML / LLMs:** PyTorch, Hugging Face Transformers, PEFT (LoRA/QLoRA), knowledge distillation, model evaluation, scikit-learn
- **NLP / retrieval:** RAG, sentence embeddings, semantic search, evidence provenance
- **Systems:** Python, Java, SQL, Linux, Slurm/HPC, FastAPI, Docker/Compose, GitHub Actions
- **Cloud / MLOps:** Google Cloud Run, AWS and Azure coursework, Terraform, Ansible, Prometheus, Grafana
