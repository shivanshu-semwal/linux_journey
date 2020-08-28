# Conda

> Conda is an open-source, cross-platform, language-agnostic package manager and environment management system.

## Getting Started

*   `conda info` : Verify Conda is installed, check version number
*   `conda update -n base conda` : Update Conda to the current version
*   `conda update anaconda` : Update all packages to the latest version of Anaconda.
*   `conda -v` : see current conda version
*   `conda update conda` : update conda

## Working with Environments

*   `conda create --name ENVNAME python=3.6 "PKG1>7.6" PKG2` : Create a new environment named ENVNAME with specific version of Python and packages installed.
*   `conda info -e` : List the environments availiable
*   `conda activate ENVNAME` : Activate a named Conda environment
*   `conda activate /path/to/environment-dir` : Activate a Conda environment at a particular location on disk
*   `conda deactivate` : Deactivate current environment 
*   `conda list` : List all packages and versions in the active environment
*   `conda list --name ENVNAME` : List all packages and versions in a named environment
*   `conda list --revisions` : List all revisions made within the active environment
*   `conda list --name ENVNAME --revisions` : List all revisions made in a specified environment
*   `conda install --name ENVNAME --revision REV_NUMBER` : Restore an environment to a previous revision
*   `conda remove --name ENVNAME --all` : Delete an entire environment

*   `conda search "^python$"` : list the availiable version of python avaliable locally
*   `conda install pip` :   install pip in currently active environment

## Jupyter Notebook

*   `python -m ipykernel install --user --name=shivanshu` : install the ipykernel so that the environment can run the jupyter notebook
