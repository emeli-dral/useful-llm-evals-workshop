# useful-llm-evals-workshop
Workshop materials for evaluating LLM-powered products with a small, practical MLflow demo.

## Demo

The demo product is an outdoor gear support assistant. The notebook compares two prompt versions on three customer questions and tracks the results in MLflow.

```text
mlflow-experiment-tracking-workshop-short.ipynb
```

It includes:

- 3 eval examples;
- 2 prompt versions;
- 2 scorers: `answer_similarity` and `house_style`;
- MLflow runs with metrics, prompts and traces.

## Setup

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
export OPENAI_API_KEY="your_api_key_here"
```

## Start MLflow

```bash
mlflow server --host 127.0.0.1 --port 5000 --backend-store-uri sqlite:///mlflow.db
```

Open:

```text
http://127.0.0.1:5000
```

## Run

```bash
jupyter lab
```

Then open:

```text
mlflow-experiment-tracking-workshop-short.ipynb
```

The notebook requires `OPENAI_API_KEY` from the start.

## Local artifacts

MLflow creates local runtime files:

```text
mlflow.db
mlruns/
mlartifacts/
```

Recommended `.gitignore`:

```gitignore
.venv/
__pycache__/
.ipynb_checkpoints/

mlflow.db
mlruns/
mlartifacts/

.env
.DS_Store
```
