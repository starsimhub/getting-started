# Getting started with Python

This guide presents three options for getting up and running with Starsim. It assumes no prior knowledge of Python. If you have used Python before and know what setup you prefer, you are always welcome to use that; Starsim works with (virtually) any Python installation.

Note: since this document assumes you have no prior Python experience, it does not discuss [virtual environments](https://code.visualstudio.com/docs/python/environments). These are useful (sometimes critical) for juggling multiple different Python projects. However, if you will primarily be working on one Python project at a time, or working on a set of projects that all have similar dependencies, you probably don't need them.


## Editor options

Before installing Starsim, you need to install a Python environment and editor.

### Option 1: VS Code (recommended)

VS Code is by far the most commonly used editor among Starsim team members due to its excellent Python and AI support.

1. Download and install [VS Code](https://code.visualstudio.com/).
2. Install the [Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python).
3. VS Code will prompt you to install Python if it's not already on your system. Alternatively, download Python from [python.org](https://www.python.org/downloads/).
4. From the terminal inside VS Code, install Starsim: `pip install starsim`
5. Check that it worked: create a file called e.g. `demo.py` with the contents `import starsim as ss; ss.demo()`, and then click on the play button at the top right of the editor. The script should run, produce text output, and produce a plot.

More info: [VS Code Python tutorial](https://code.visualstudio.com/docs/python/python-tutorial)

### Option 2: Conda-forge + Spyder

If you are coming from an RStudio background, Spyder might feel most familiar to you. Compared to VS Code, it's very basic (and lacks AI support), but it excels at quickly running scripts and working in the command line. Some people use VS Code for AI-heavy workflows, and then switch to Spyder for quick interactive development and debugging.

1. Install [Miniforge](https://conda-forge.org/download/). This will add the commands `python`, `conda`, and `pip` (among others) to your terminal.
2. From your terminal, install Spyder: `conda install spyder`
3. Install Starsim: `pip install starsim`
4. Check that it worked: from the Spyder console, run `import starsim as ss; ss.demo()`. This should produce text output and produce a plot. (Note: if you want your plots to appear as new windows rather than in the "Plots" pane, you can change this option under Tools → Preferences.)

More info: [Conda getting started](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html) | [Spyder docs](https://docs.spyder-ide.org/)

_Note:_ If you want to use both Spyder and VS Code, install Conda + Spyder first, then install VS Code. This ensures that VS Code uses the same Python installation as Spyder.


## Package management: pip vs uv

The instructions above use `pip`, which is the standard Python package installer that comes bundled with Python. However, you may increasingly see projects provide instructions for using `uv` instead:
```bash
# Install uv (see https://docs.astral.sh/uv/)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Use it like pip
uv pip install somepackage
```

`uv` is much faster than `pip`, but if you're reading this guide, the difference is almost certainly going to be negligble to you since you are unlikely to be creating new Python environments multiple times a day. The two tools are interchangeable, so use whichever you prefer.
