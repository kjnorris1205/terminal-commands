# uv Commands for Beginners

A quick guide to using **uv** — a fast Python package and project manager.

---

## What is uv?

`uv` is a modern tool that replaces `pip`, `pip-tools`, `venv`, and more. It's extremely fast and handles Python projects from start to finish.

### Install uv
```bash
# Windows (PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh
```

---

## Managing Python Versions

### Install a specific version of Python
```bash
uv python install 3.12
```

### List available Python versions
```bash
uv python list
```

### Check which Python uv will use
```bash
uv python find
```

---

## Projects (Recommended Way to Work)

### Create a new project
```bash
uv init my-project
cd my-project
```

This creates a folder with a `pyproject.toml`, a `README.md`, and a starter `main.py`.

### Add a package to your project
```bash
uv add requests
uv add pandas numpy        # add multiple at once
uv add pytest --dev        # add a dev-only dependency
```

### Remove a package
```bash
uv remove requests
```

### Install all dependencies (from an existing project)
```bash
uv sync
```

### Run your project's script
```bash
uv run main.py
```

### Run a tool or command inside the project environment
```bash
uv run pytest
uv run python
```

> **Tip:** `uv run` automatically sets up the virtual environment for you — no need to activate it manually.

---

## Virtual Environments (Manual)

If you prefer managing environments yourself:

### Create a virtual environment
```bash
uv venv
```

### Create one with a specific Python version
```bash
uv venv --python 3.12
```

### Activate the environment
```bash
# Windows (PowerShell)
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate
```

---

## Installing Packages (pip-style)

You can use uv as a drop-in replacement for pip:

### Install a package
```bash
uv pip install requests
```

### Install from a requirements file
```bash
uv pip install -r requirements.txt
```

### Uninstall a package
```bash
uv pip uninstall requests
```

### List installed packages
```bash
uv pip list
```

### Show info about a package
```bash
uv pip show requests
```

---

## Running One-Off Tools

Run a command-line tool without installing it permanently:

```bash
uvx ruff check .          # run the ruff linter
uvx black .               # run the black formatter
uvx httpie GET example.com
```

> **Tip:** `uvx` is a shortcut for `uv tool run`. Great for trying tools without cluttering your environment.

---

## Quick Reference

| Task | Command |
|---|---|
| Install Python 3.12 | `uv python install 3.12` |
| Create a new project | `uv init my-project` |
| Add a package | `uv add requests` |
| Remove a package | `uv remove requests` |
| Install all dependencies | `uv sync` |
| Run a script | `uv run main.py` |
| Create a virtual env | `uv venv` |
| Install package (pip-style) | `uv pip install requests` |
| Run a tool without installing | `uvx ruff check .` |
