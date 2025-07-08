# Medical QA Benchmark

This repository contains the code for the Medical QA Benchmark.

## Setup

```bash
git clone https://github.com/medqa-benchmark/medical-qa-benchmark.git

cd medical-qa-benchmark

uv init

uv pip install -e .
```

## License

MIT 2.0

## Repo Structure

```
medical-qa-benchmark/
├── README.md                  # Project overview, usage, features
├── LICENSE                    # Apache 2.0 license
├── .gitignore                 # Ignore cache, logs, etc.
├── Makefile                   # Easy CLI entrypoints for common tasks
├── requirements.txt           # Runtime dependencies
├── pyproject.toml             # uv-based dependency manager

├── configs/                   # YAML configs to control experiments
│   └── experiment_template.yaml

├── data/
│   ├── download/              # Raw downloaded files (if any)
│   ├── processed/             # Preprocessed/chunked data
│   └── loaders/               # Dataset-specific loaders
│       ├── base_loader.py
│       ├── med_qa_loader.py
│       └── medmcqa_loader.py

├── evaluation/
│   ├── evaluators/            # Task-specific evaluation logic
│   │   ├── general_qa.py
│   │   ├── mcq_qa.py
│   │   └── metrics.py
│   └── visualizer.py          # Charts and visualizations

├── experiments/
│   ├── run_experiment.py      # Config-driven main entrypoint
│   └── run_from_colab.ipynb   # Colab-compatible runner

├── finetune/
│   ├── trainer.py
│   ├── lora.py
│   ├── qlora.py
│   └── utils.py

├── inference/
│   ├── zero_shot.py
│   ├── rag.py
│   ├── chunkers/
│   │   ├── chunker_v1.py
│   │   └── chunker_v2.py
│   ├── rerankers/
│   │   ├── bge.py
│   │   └── cohere.py
│   └── pipeline.py            # Assembles RAG blocks into execution

├── models/
│   └── load_model.py          # Base model loader for all strategies

├── retrieval/
│   ├── chroma_db.py           # DB builder using Chroma
│   ├── embedder.py
│   └── retriever.py

├── reporting/
│   ├── logger.py              # Unified logger interface
│   └── wandb_tracker.py       # Optional wandb logging

├── utils/
│   ├── seed.py
│   ├── config.py              # Config loader
│   └── constants.py           # Reusable constants
```

## How to run

