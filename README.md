# Jupyter-Notebooks

## What is Jupyter?
- Jupyter is a web application that allows you to display and execute Python interactively. The interface is writteni n CSS, HTML and JavaScript. This run in a web browser on the client machine.

## Installation
- It can be installed via pip as: `pip install jupyter`
- To see which jupter is being used use: `which jupyter`
- To launch Jupyter type: `jupyter notebook`

## How to create a virtual environment with conda
- See which conda you are using (meaning it shows the path of the executable being called): `which conda`
- Create a virtual environment using conda specific command: `conda create –-name my_env_name python=3.7` (check for the last stable Python realease [here](https://www.python.org/downloads/macos/))
- Activate the virtual environment: `conda activate my_env_name` 
- How to visualise all the env available: `conda env list`
- Install any package you like via these two options: `conda install package_name` or `pip package_name`
- How to delete a virtual env: `conda env remove --name=my_env_name`

## How to manage python packages
- Update a to a specific module version: `scikit-learn==0.24.1 –upgrade`
- How to revert to an older version: first `pip uninstall scikit-learn` then `pip install scikit-learn==0.18.2`

## How to activate a specific env within your jupyter notebook
- All command lines were taken form this [Ref#1](https://medium.com/@nrk25693/how-to-add-your-conda-environment-to-your-jupyter-notebook-in-just-4-steps-abeab8b8d084) and [Ref#2](https://janakiev.com/blog/jupyter-virtual-envs/)
- Let us assume we have a number of different virtual environments in our machine and we’d like to remind ourself what these are. Type on the console: `conda env list` and hopefully more than one virt env will be shown. Now let us assume I'd like to use one of them in my Jupyter notebook.
- Activate your virtual environment: `conda activate my_specific_virt_env_name`
- Install `ipykernel` as: `conda install -c anaconda ipykernel`
- Add you virtual env to your ipykernel: `python -m ipykernel install --user --name=my_specific_virt_env_name`
- Now your new env will be shown in the drop down menu under `New`.

![image](https://user-images.githubusercontent.com/89139139/150124430-456ce370-12ca-4eab-8504-cefeda2e8194.png)

- To list of the env available to jupiter use: `jupyter kernelspec list`
- To remove one env use: `jupyter kernelspec uninstall name_of_env_not_needed`

## How to install Jupyter extentions
- Run this command to install notebook extensions: `pip install jupyter_contrib_nbextensions && jupyter contrib nbextension install`. If you get an error like this `Permission denied: '/usr/local/share'` try this instead as suggested [here](https://github.com/Calysto/matlab_kernel/issues/68): `pip install jupyter_contrib_nbextensions && jupyter contrib nbextension install --user`
- Start up a Jupyter Notebook and navigate to the new Nbextensions tab:
![image](https://user-images.githubusercontent.com/89139139/150533233-ddc25295-9f2b-43b6-aea0-305cb0a497cd.png)
- If you don’t see a tab, open a notebook and click Edit > nbextensions config.
[Ref](https://towardsdatascience.com/jupyter-notebook-extensions-517fa69d2231)

## Useful notebook extentions
- **Tabel of contents**: Once you start getting dozens of cells in one Jupyter Notebook, it can be difficult to keep track of them all. The Table of Contents solves that problem by adding a linked TOC that can be positioned anywhere on the page.
- **Autopep8**: use kernel-specific code to reformat/prettify the contents of code cells. Apart from activating the `Autopep8` extention under `Nbextentions` make sure you run this as well: `pip install autopep8`
- **Variable Inspector** extension collects all defined variables and display them in a floating window. The extension is also draggable, resizable, collapsable.
- **ExecuteTime** shows when and how long cells ran.
- **Hide Code input** hides the work show the results.
- **Code Folding** clicking on the triangle in the gutter (left margin of codecell).

## How to publish your notebook
- Let's assume you have loaded your notebook file (.ipynb) on GitHub
- Navigate to `https://nbviewer.org/` past your notebook's URL on this will return a fully rendered notebook.
- If you prefer to do it via command line [here](https://reproducible-science-curriculum.github.io/publication-RR-Jupyter/02-exporting_the_notebook/index.html) are the instructions.

## How to convert your notebook to pdf
- [Jupyter Notebooks(ipynb) Viewer and Converter](https://htmtopdf.herokuapp.com/ipynbviewer/)

## List of Jupyter Notebook Tips, Tricks, and Shortcuts
- [28 Jupyter Notebook Tips, Tricks, and Shortcuts](https://www.dataquest.io/blog/jupyter-notebook-tips-tricks-shortcuts/)

