# Getting started with Python

## Installation options

### Option 1: VS Code (recommended)

VS Code is a free, lightweight code editor with excellent Python support. It provides an integrated terminal, debugging, linting, and AI assistance all in one place.

1. Download and install [VS Code](https://code.visualstudio.com/).
2. Install the [Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python).
3. VS Code will prompt you to install Python if it's not already on your system. Alternatively, download Python from [python.org](https://www.python.org/downloads/).

More info: [VS Code Python tutorial](https://code.visualstudio.com/docs/python/python-tutorial)

### Option 2: Conda-forge + Spyder

Conda is a package and environment manager popular in scientific computing. Spyder is a MATLAB-like IDE designed for data science workflows.

1. Install [Miniforge](https://conda-forge.org/download/) (a lightweight conda installer that uses the conda-forge channel by default).
2. Create an environment: `conda create -n myenv python`
3. Activate it: `conda activate myenv`
4. Install Spyder: `conda install spyder`

More info: [Conda getting started](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html) | [Spyder docs](https://docs.spyder-ide.org/)

### Option 3: Command line

If you prefer working in the terminal:

1. Install Python from [python.org](https://www.python.org/downloads/) or via your system package manager.
2. Run scripts with `python myscript.py`.
3. Use the interactive interpreter with `python` or `ipython` (install via `pip install ipython`).


## Package management: pip vs uv

**pip** is the standard Python package installer that comes bundled with Python. It's well-established and universally supported:
```bash
pip install somepackage
```

**uv** is a newer, much faster alternative to pip written in Rust. It's a drop-in replacement that also handles virtual environments:
```bash
# Install uv (see https://docs.astral.sh/uv/)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Use it like pip
uv pip install somepackage
```

Either tool works fine. uv is faster for large installs but pip is more widely documented. Use whichever you prefer.


## Installing Starsim

With pip:
```bash
pip install starsim
```

With uv:
```bash
uv pip install starsim
```

To install the development version directly from GitHub:
```bash
pip install git+https://github.com/starsimhub/starsim.git
```

Verify the installation:
```bash
python -c "import starsim as ss; print(ss.__version__)"
```
