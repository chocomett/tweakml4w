# 🐍 05. Python

This guide installs Python and sets up a modern development environment using `uv`.

**⏱️ Estimated Time:** 10–15 minutes

---

## Step 1. Install Python

Install Python, pip, and uv from the official repositories.

```bash
sudo pacman -S \
python \
python-pip \
uv
```

### What are these packages?

| Package | Description |
| ------- | ----------- |
| `python` | The Python programming language. |
| `python-pip` | The default Python package manager. Some projects still use it. |
| `uv` | A modern package and virtual environment manager that replaces most everyday uses of `pip` and `venv`. It is significantly faster and fully compatible with existing Python projects. |

---

## Step 2. Verify Installation

Verify that everything is installed correctly.

```bash
python --version
pip --version
uv --version
```

---

## Step 3. Create a Project

Create a new project directory.

```bash
mkdir my-project
cd my-project
```

Create a virtual environment.

```bash
uv venv
```

This creates a `.venv` directory inside your project.

Activate the virtual environment.

```bash
source .venv/bin/activate
```

Deactivate it when you are finished.

```bash
deactivate
```

---

## Step 4. Install Packages

Install packages using `uv`.

```bash
uv pip install requests
```

Example:

```bash
uv pip install numpy pandas matplotlib
```

---

## Step 5. Run Python

Create a file.

```text
hello.py
```

Example:

```python
print("Hello, World!")
```

Run it.

```bash
python hello.py
```

---

## Verify

Check that Python can import installed packages.

```bash
python -c "import requests; print(requests.__version__)"
```

---

## Notes

> 💡 I use `uv` instead of the traditional `pip` + `venv` workflow because it is significantly faster while remaining fully compatible with Python projects.

> 💡 Every project should have its own virtual environment.

> 💡 Never install project dependencies globally unless absolutely necessary.

---

## Useful Commands

### Python

| Purpose | Command |
| ------- | ------- |
| Show Python version | `python --version` |
| Start Python REPL | `python` |
| Run a Python script | `python script.py` |
| Show installed modules | `python -m pip list` |

Example:

```bash
python app.py
```

---

### Virtual Environment

| Purpose | Command |
| ------- | ------- |
| Create a virtual environment | `uv venv` |
| Activate the environment | `source .venv/bin/activate` |
| Deactivate the environment | `deactivate` |
| Remove the environment | `rm -rf .venv` |

Example:

```bash
uv venv

source .venv/bin/activate
```

---

### Package Management

| Purpose | Command |
| ------- | ------- |
| Install a package | `uv pip install package` |
| Upgrade a package | `uv pip install --upgrade package` |
| Remove a package | `uv pip uninstall package` |
| List installed packages | `uv pip list` |
| Export dependencies | `uv pip freeze > requirements.txt` |
| Install from requirements | `uv pip install -r requirements.txt` |

Example:

```bash
uv pip install requests

uv pip list
```

---

## Understanding uv

### Traditional Python Workflow

Create a virtual environment.

```bash
python -m venv .venv
```

Activate it.

```bash
source .venv/bin/activate
```

Install packages.

```bash
pip install requests
```

---

### Modern Workflow with uv

Create a virtual environment.

```bash
uv venv
```

Activate it.

```bash
source .venv/bin/activate
```

Install packages.

```bash
uv pip install requests
```

The result is exactly the same, but `uv` performs dependency resolution and package installation much faster than the traditional workflow.

---

## Troubleshooting

### ❌ uv: command not found

Verify that uv is installed.

```bash
uv --version
```

Reinstall it if necessary.

```bash
sudo pacman -S uv
```

---

### ❌ ModuleNotFoundError

The package is not installed in the current virtual environment.

```bash
uv pip install package_name
```

---

### ❌ Virtual environment is not activated

Activate it again.

```bash
source .venv/bin/activate
```

---

## Next

➡️ **06-zsh.md**