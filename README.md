# Builder vs. Breaker (LangGraph, open‑source LLMs)

A reproducible agentic pipeline that adversarially improves a small Python repo.
- **Builder** patches code with ReAct tool use.
- **Breaker** adds failing/property-based tests.
- **Critic** gates risky edits.
- **Referee** runs sandboxed `pytest` + `ruff check .`.
- **Debate** step: Builder hypothesis ↔ Breaker counterexample.
- **Reflexion** memory logs.

## Quickstart (Colab)
1. Open the notebook in this repo (or your own):  
   **File → Open notebook → GitHub → paste repo URL**, or use the badge below.
2. Set Runtime → T4 GPU (optional but faster).
3. Run cells top-to-bottom.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/USER/REPO/blob/main/notebooks/builder_vs_breaker_colab.ipynb)

## Local (Mac/Linux)
```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python notebooks/runner_stub.py   # or open the .ipynb in VS Code
```

## Repo layout
```
builder-vs-breaker/
├─ notebooks/
│  ├─ builder_vs_breaker_colab.ipynb     # download from Colab: File → Download .ipynb
│  └─ runner_stub.py                      # tiny entrypoint to run one duel locally
├─ demo_repo/                             # tiny target codebase used in the demo
├─ src/                                   # optional: place your reusable modules here
├─ requirements.txt
├─ .gitignore
├─ LICENSE (MIT)
└─ README.md
```

## Notes
- Artifacts (logs/diffs) are not committed by default (`artifacts/` is gitignored).
- To change models: edit SMALL_MODEL_ID / BIG_MODEL_ID in the notebook (Qwen2.5-Coder by default).
- For GitHub Actions or Docker, add those later—this repo is kept simple for now.
