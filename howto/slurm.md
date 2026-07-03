# Running Python on Slurm

A Slurm cluster typically has Python (often, many versions) already installed. However, they might be quite old. You will want to use a Python environment manager (conda, mamba, or uv) to install and manage a newer version of Python.

The first step is to load the module that has the appropriate environment manager (if no such module exists, the cluster administrator will likely need to install it). This could look something like

```
module load mamba3
```

The exact name of the module will vary depending on the cluster setup. You can use `module avail` to list available modules, and hopefully one of them will "look" right.

If you're using `uv`, from here you can proceed to use it normally -- e.g. `cd ~/myproject; uv sync`.

If you're using conda/mamba, you might need to set up the package path to point to your home folder rather than wherever conda/mamba is installed. The best way to do this is to configure a `.condarc` file. Let's say that on your cluster's filesystem, your folder on the shared drive (that both the head and compute nodes have access to) is called `/shared_folder/username/`. Then you would put this as your `.condarc` file:

```
channels:
  - conda-forge

channel_priority: strict

envs_dirs:
  - /shared_folder/username/conda/envs

pkgs_dirs:
  - /shared_folder/username/conda/pkgs
```

Once this is set up, create a Python environment as usual:

```
mamba create -n myproj python=3.13 numpy scipy
```

Then you can activate the environment (you might need `mamba init` or `conda init` first):

```
mamba activate myproj
```

Finally, install the package you want to use -- if this is a cloned GitHub repo, you would want to do something like

```
cd myrepo
pip install -e .
```

This installs it in "editable mode" (`-e`), so to update the package, you just need to do `git pull`.

To run on a compute node, you just need to do the step `mamba activate myproj` and then proceed as you would locally.
