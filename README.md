# Assignment 2 - Alzheimer's Disease Data Analysis

This project uses UV for Python package management. UV is a fast, reliable package and project manager that replaces pip and other Python tools.

## Prerequisites

- Python 3.14 or higher
- UV package manager

## Installing UV

UV can be installed on Windows using several methods:

### Option 1: WinGet (Recommended for Windows)

```powershell
winget install --id=astral-sh.uv -e
```

### Option 2: PowerShell Installer

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### Option 3: Scoop

```powershell
scoop install main/uv
```

### Option 4: pip

```powershell
pip install uv
```

After installation, verify UV is installed correctly:

```powershell
uv --version
```

## Project Setup

### 1. Clone the Project

```
git clone git@github.com:Jelles/AML-Assignment-2.git
```

### 2. Sync Dependencies

To install all project dependencies listed in `pyproject.toml`:

```powershell
uv sync
```

This command will:
- Create a virtual environment (if not exists)
- Install all dependencies specified in `pyproject.toml`
- Generate/update the `uv.lock` file

## Managing Packages

### Adding New Packages

To add a new package to the project:

```powershell
uv add package-name
```

For example, to add numpy:

```powershell
uv add numpy
```

To add a package with a specific version:

```powershell
uv add "package-name>=1.0.0"
```

### Adding Development Dependencies

For packages only needed during development (testing, linting, etc.):

```powershell
uv add --dev package-name
```

### Removing Packages

```powershell
uv remove package-name
```

### Updating Packages

To update all packages to their latest compatible versions:

```powershell
uv lock --upgrade
uv sync
```

To update a specific package:

```powershell
uv lock --upgrade-package package-name
uv sync
```

## Running the Project

### Running Python Scripts

```powershell
uv run python script.py
```

### Running Jupyter Notebooks

```powershell
uv run jupyter notebook
```

Or to launch Jupyter Lab:

```powershell
uv run jupyter lab
```

### Running Commands in the Virtual Environment

Any command can be run in the project's virtual environment:

```powershell
uv run command
```

## Current Dependencies

This project currently includes:
- **ipykernel** (>=7.1.0) - Jupyter kernel
- **matplotlib** (>=3.10.7) - Plotting library
- **outliertree** (>=1.10.0.post2) - Outlier detection
- **pandas** (>=2.3.3) - Data manipulation
- **scikit-learn** (>=1.7.2) - Machine learning

## Project Structure

```
Assignment 2/
├── main.ipynb                          # Main Jupyter notebook
├── pyproject.toml                      # Project configuration and dependencies
├── uv.lock                             # Locked dependencies (auto-generated)
├── README.md                           # This file
└── data/
    ├── alzheimers_disease_data.csv    # Dataset
    └── Dataset attribute description.txt
```

## Useful UV Commands

| Command | Description |
|---------|-------------|
| `uv sync` | Install/sync all dependencies |
| `uv add package-name` | Add a new package |
| `uv remove package-name` | Remove a package |
| `uv lock` | Update the lock file |
| `uv run command` | Run a command in the virtual environment |
| `uv pip list` | List installed packages |
| `uv self update` | Update UV itself |

## Troubleshooting

### Virtual Environment Issues

If you encounter virtual environment issues, you can reset it:

```powershell
Remove-Item -Recurse -Force .venv
uv sync
```

### Cache Issues

Clear UV's cache if you encounter download or installation issues:

```powershell
uv cache clean
```

## Additional Resources

- [UV Documentation](https://docs.astral.sh/uv/)
- [UV Getting Started Guide](https://docs.astral.sh/uv/getting-started/first-steps/)
- [UV Project Guide](https://docs.astral.sh/uv/guides/projects/)
