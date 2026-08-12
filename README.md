# py-project-starter

A modern Python starter template for new projects and experiments. It includes uv dependency management, Ruff linting and formatting, pytest with coverage, and GitHub Actions continuous integration.

## 📋 Core Components

- `pyproject.toml`: Project metadata, dependencies, supported Python version, build configuration, and settings for Ruff and pytest.
- uv: The project and dependency manager. It creates the local environment, installs dependencies, and runs project tools.
- Ruff: A fast Python linter and formatter. It identifies code-quality issues, can automatically fix many of them, and verifies consistent code formatting.
- GitHub Actions: The workflow in `.github/workflows/ci.yml` runs automated checks on pushes and pull requests.
- `.venv`: The local virtual environment created by `uv sync`. Do not commit it to Git.
- `uv.lock`: The dependency lock file that records exact package versions. Commit it to Git so development and CI use the same dependencies.

## 📈 Future Roadmap

- Placeholder for template

## 📂 Project Structure

```text
py-project-starter/
├── .github/
│   └── workflows/
│       └── ci.yml          # Continuous integration workflow
├── project_name/           # Application package
│   ├── utils/              # Reusable helper modules
│   ├── __init__.py         # Public package interface
│   └── main.py             # Application entry point
├── tests/                  # Test suite
├── docs/                   # Documentation
├── .env.example            # Environment variable template
├── .gitignore              # Git ignore rules
├── pyproject.toml          # Project and tool configuration
├── README.md               # Project documentation
└── uv.lock                 # Locked dependency versions
```

## 🚀 Getting Started

### 1. Install Requirements

You need Python 3.12 or later, Git, and [uv](https://docs.astral.sh/uv/).

Install uv on Windows:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Install uv on Linux or macOS:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### 2. Clone the Repository

```powershell
git clone "https://github.com/henrysrtaylor/py-project-starter.git"
cd py-project-starter
```

### 3. Install Dependencies

From the project root, create or update the local virtual environment and install dependencies:

```powershell
uv sync
```

### 4. Run Quality Checks

Run the linter and automatically apply safe fixes:

```powershell
uv run ruff check . --fix
```

Verify that the code is correctly formatted:

```powershell
uv run ruff format --check .
```

Run the test suite and display coverage for any untested lines:

```powershell
uv run pytest --cov=project_name --cov-report=term-missing
```