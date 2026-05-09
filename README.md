# GitHub Actions Demo

A minimal Python project demonstrating a full CI/CD pipeline with GitHub Actions.

## Features

- Utility functions: `greet`, `add`, `is_even`
- Pytest test suite with coverage reporting
- CI/CD pipeline: lint (flake8, black, isort), test matrix (Python 3.9–3.11), and packaging

## Requirements

- Python 3.9+
- Dependencies listed in `requirements.txt`

## Setup

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Run

```bash
python hello.py
```

## Test

```bash
pytest --cov=hello
```

## CI/CD

The workflow in `.github/workflows/devops.yml` runs on every push to `main`/`develop` and on pull requests to `main`:

| Job | What it does |
|-----|-------------|
| `test` | Runs pytest across Python 3.9, 3.10, 3.11 with coverage upload |
| `lint` | Checks style with flake8, black, and isort |
| `package` | Zips the app and uploads it as a release artifact (main only) |
