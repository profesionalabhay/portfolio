# AI & Machine Learning Development Environment

## Overview

This repository is configured for browser-based AI and Machine Learning development using GitHub Codespaces, eliminating the need for local setup.

## Quick Start

### 1. Launch Codespace

1. Click the **Code** button in the repository
2. Navigate to the **Codespaces** tab
3. Click **Create codespace on main**
4. Wait for the environment to initialize (2-5 minutes)

### 2. Work in VS Code Web

Once the Codespace loads, you'll have a complete development environment with:
- Python 3.11
- Pre-installed ML libraries (TensorFlow, PyTorch, scikit-learn, pandas, numpy)
- GitHub Copilot for AI-assisted coding
- Jupyter notebook support
- Git integration

## Environment Components

### Development Container Configuration
**File:** `.devcontainer/devcontainer.json`

Configures:
- Python 3.11 base image
- Essential VS Code extensions for Python and ML
- Auto-installation of ML frameworks
- Port forwarding for Jupyter (8888), Flask (5000), and FastAPI (8000)
- Git and GitHub CLI integration

### Python Dependencies
**File:** `requirements.txt`

Includes:
- **Core ML:** NumPy, Pandas, scikit-learn, SciPy
- **Deep Learning:** TensorFlow, PyTorch, Transformers
- **Visualization:** Matplotlib, Seaborn, Plotly
- **Notebooks:** Jupyter, IPython
- **Web Frameworks:** Flask, FastAPI
- **Testing:** Pytest, Black, Pylint
- **Experiment Tracking:** MLflow, W&B
- **Data Versioning:** DVC

### .gitignore
**File:** `.gitignore`

Ignores:
- Python cache files
- Virtual environments
- ML model files (.pkl, .h5, .pth, .pb)
- Large datasets (.csv, .xlsx)
- Notebook checkpoints
- IDE files (.vscode, .idea)

## Installed VS Code Extensions

- **Python** - Official Python support
- **Pylance** - Static type checking
- **Jupyter** - Notebook integration
- **GitHub Copilot** - AI code completion
- **Copilot Chat** - Conversational AI assistance
- **GitLens** - Git version control
- **Black Formatter** - Code formatting
- **Ruff** - Linting

## CI/CD with GitHub Actions

**File:** `.github/workflows/python-tests.yml`

Automatically runs on push/PR:
- ✅ Tests on Python 3.9, 3.10, 3.11
- ✅ Code formatting (Black)
- ✅ Linting (Flake8, Pylint)
- ✅ Unit tests (Pytest with coverage)
- ✅ Security checks (Bandit, Safety)
- ✅ Coverage reports (Codecov)

## Workflow Guide

### 1. Creating a New ML Project

```bash
# Inside your codespace terminal
mkdir my_project
cd my_project

# Start with a Jupyter notebook
jupyter notebook
```

### 2. Running Tests

```bash
pytest
pytest --cov  # With coverage
```

### 3. Using GitHub Copilot

- **Inline suggestions:** Start typing, Copilot suggests completions
- **Copilot Chat:** `Ctrl+Shift+I` to open chat panel
- Common prompts:
  - "Write a function to load CSV data"
  - "Create a train/test split"
  - "Implement cross-validation"

### 4. Pushing Code

```bash
git add .
git commit -m "Add my ML model"
git push origin main
```

GitHub Actions automatically tests your code!

### 5. Running Web Apps

**Flask:**
```bash
python app.py  # Runs on port 5000
```

**FastAPI:**
```bash
uvicorn main:app --reload  # Runs on port 8000
```

## Project Structure Recommendations

```
project/
├── data/
│   ├── raw/
│   ├── processed/
│   └── external/
├── notebooks/
│   ├── 01-data-exploration.ipynb
│   ├── 02-feature-engineering.ipynb
│   └── 03-model-training.ipynb
├── src/
│   ├── data/
│   │   ├── __init__.py
│   │   └── loader.py
│   ├── models/
│   │   ├── __init__.py
│   │   └── train.py
│   └── evaluation/
│       ├── __init__.py
│       └── metrics.py
├── tests/
│   ├── test_data.py
│   ├── test_models.py
│   └── test_evaluation.py
├── config.yaml
├── requirements.txt
├── setup.py
└── README.md
```

## Experiment Tracking

### MLflow
```python
import mlflow

with mlflow.start_run():
    mlflow.log_param("lr", 0.01)
    mlflow.log_metric("accuracy", 0.95)
    mlflow.log_artifact("model.pkl")
```

### Weights & Biases
```python
import wandb

wandb.init(project="my-project")
wandb.log({"loss": 0.5, "accuracy": 0.95})
```

## Common Issues & Troubleshooting

### Codespace Takes Long to Load
- First load can take 2-5 minutes
- Subsequent loads are faster (~30s)
- Prebuilds available in settings to speed up

### Extension Not Working
- Extensions may need rebuilding
- Try: Command Palette → "Developer: Reload Window"

### Memory Issues
- Use smaller models for testing
- Upgrade Codespace machine type if needed

## Benefits

✅ **No Local Setup** - Pure cloud-based development
✅ **Always Updated** - Latest Python and libraries
✅ **AI Assistance** - GitHub Copilot included
✅ **Consistency** - Same environment for all developers
✅ **Scalability** - Easy to upgrade compute
✅ **Integration** - Full GitHub integration
✅ **Cost Effective** - Free hours included, pay-per-use after

## Next Steps

1. **Create a Codespace** and verify all extensions load
2. **Clone or create** a sample ML notebook
3. **Commit and push** to trigger GitHub Actions
4. **Monitor** the workflow run in Actions tab
5. **Start building** your AI/ML projects!

## Resources

- [GitHub Codespaces Docs](https://docs.github.com/en/codespaces)
- [Dev Containers](https://containers.dev/)
- [Python ML Resources](https://scikit-learn.org/)
- [GitHub Copilot Guide](https://github.com/features/copilot)

---

**Last Updated:** February 26, 2026
**Version:** 1.0
