# Jupyter-Notebooks
***

## What is Jupyter?
- Jupyter is a web application that allows you to display and execute Python interactively. The interface is writteni n CSS, HTML and JavaScript. This run in a web browser on the client machine.
***

## Why Jupyter?
- Seeing intermediate (debugging) results for each step of the analysis 
- Running only some sections (or cells) of the code 
- Storing intermediate results in the JSON format and having the ability to do version control on them 
- Presenting your work (this will be a combination of text, code, and images), sharing it via the [Jupyter Notebook Viewer service](http://nbviewer. jupyter.org/), and easily exporting it to HTML, PDF, or even slideshows 
***

## When not to use Jupyter?
- Jupyter notebooks are great for quick exploration of the data you are working with, but do not use them as your main development tool.
- Notebooks do not encourage a reproducible workflow, and you should see this talk for a good overview of why they don’t.
- Use a proper IDE like PyCharm or VS code (or vim if you’re into that) when developing code. Convince your employer to buy you professional editions of this software (this is usually peanuts for the company, and can be a massive productivity boost). I develop most of my code locally, but use PyCharm’s remote execution to execute any code on the cloud or an internal VM.
***

## Installation
- It can be installed via pip as: `pip install jupyter`
- To see which jupter is being used use: `which jupyter`
- To launch Jupyter type: `jupyter notebook`
***

## How to create a virtual environment with conda
- See which conda you are using (meaning it shows the path of the executable being called): `which conda`
- Create a virtual environment using conda specific command: `conda create –-name my_env_name python=3.7` (check for the last stable Python realease [here](https://www.python.org/downloads/macos/))
- Activate the virtual environment: `conda activate my_env_name` 
- How to visualise all the env available: `conda env list`
- Install any package you like via these two options: `conda install package_name` or `pip package_name`
- How to delete a virtual env: `conda env remove --name=my_env_name`
***

## How to manage python packages
- Update a to a specific module version: `scikit-learn==0.24.1 –upgrade`
- How to revert to an older version: first `pip uninstall scikit-learn` then `pip install scikit-learn==0.18.2`
- Uograde a package: `pip install --upgrade <package_name>`
***

## Issue installing python packages
- This a list of methods I use to install packages. If one fails I move to the next suggested one:
- `pip install package_name`
- `pip3 install package_name`
- `conda install package_name`
- Last resort (installing form source): `git clone package_name`, `cd package_name` and `python setup.py install`
***

## Telling pip what to download
-  You can use `pip download` rather than `pip install` so that you can inspect the resulting wheel, but the flags will work with either of them.
```
$ pushd "$(mktemp -d)"
$ python -m pip download --only-binary :all: --dest . --no-cache <package_name>
```
- `pushd "$(mktemp -d)"` change to a temporary directory to store the download files.
- `--only-binary :all`: tells pip to constrain itself to using wheels and ignore source distributions. Without this option, pip will only prefer wheels but will fall back to source distributions in some scenarios.
- `--dest .` tells pip to download to the current directory.
- `--no-cache` tells pip not to look in its local download cache.
***

## Checking installed package version
- `pip list | grep <name of the package>`
***

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
***

## How to install Jupyter extentions
- Run this command to install notebook extensions: `pip install jupyter_contrib_nbextensions && jupyter contrib nbextension install`. If you get an error like this `Permission denied: '/usr/local/share'` try this instead as suggested [here](https://github.com/Calysto/matlab_kernel/issues/68): `pip install jupyter_contrib_nbextensions && jupyter contrib nbextension install --user`
- Start up a Jupyter Notebook and navigate to the new Nbextensions tab:
![image](https://user-images.githubusercontent.com/89139139/150533233-ddc25295-9f2b-43b6-aea0-305cb0a497cd.png)
- If you don’t see a tab, open a notebook and click Edit > nbextensions config.
[Ref](https://towardsdatascience.com/jupyter-notebook-extensions-517fa69d2231)
***

## Useful notebook extentions
- **Tabel of contents**: Once you start getting dozens of cells in one Jupyter Notebook, it can be difficult to keep track of them all. The Table of Contents solves that problem by adding a linked TOC that can be positioned anywhere on the page.
- **Autopep8**: use kernel-specific code to reformat/prettify the contents of code cells. Apart from activating the `Autopep8` extention under `Nbextentions` make sure you run this as well: `pip install autopep8`
- **Variable Inspector** extension collects all defined variables and display them in a floating window. The extension is also draggable, resizable, collapsable.
- **ExecuteTime** shows when and how long cells ran.
- **Hide Code input** hides the work show the results.
- **Code Folding** clicking on the triangle in the gutter (left margin of codecell).
***

## How to publish your notebook
- Let's assume you have loaded your notebook file (.ipynb) on GitHub
- Navigate to `https://nbviewer.org/` past your notebook's URL on this will return a fully rendered notebook.
- If you prefer to do it via command line [here](https://reproducible-science-curriculum.github.io/publication-RR-Jupyter/02-exporting_the_notebook/index.html) are the instructions.
***

## Modularise your Notebook into Scripts
- [From notebook to module](https://towardsdatascience.com/modularise-your-notebook-into-scripts-5d5ccaf3f4f3)
***

## How to convert your notebook to pdf
- [Jupyter Notebooks(ipynb) Viewer and Converter](https://htmtopdf.herokuapp.com/ipynbviewer/)
***

## How to run your notebook in parallel
- [Time Series Forecasting with Ploomber, Arima, Python, and Slurm](https://www.kdnuggets.com/2022/03/time-series-forecasting-ploomber-arima-python-slurm.html)
***

## Tips, Tricks, and Shortcuts
- [28 Jupyter Notebook Tips, Tricks, and Shortcuts](https://www.dataquest.io/blog/jupyter-notebook-tips-tricks-shortcuts/)
- [8 surprising ways how to use Jupyter Notebook](https://mljar.com/blog/how-to-use-jupyter-notebook/)
- [How to create a dashboard in Python with Jupyter Notebook?](https://mljar.com/blog/dashboard-python-jupyter-notebook/)
- [5 ways to schedule Jupyter Notebook](https://mljar.com/blog/schedule-jupyter-notebook/)
***

## Pip vs. Conda
- Pip installs Python packages whereas conda installs packages which may contain software written in any language. 
- Conda` can install Python packages as well as the Python interpreter directly whereas pip installs only python packages.
- Conda has the ability to create isolated environments that can contain different versions of Python and/or the packages installed in them. Pip has no built in support for environments but rather depends on other tools like virtualenv or venv to create isolated environments. 

***

## Mixing Pip and Conda
- When some packages are only available to install via pip. 
- Over *1,500* packages are available in the Anaconda repository, including the most popular data science, machine learning, and AI frameworks. These, along with thousands of additional packages available on Anaconda cloud from channeling including conda-forge and bioconda, can be installed using conda. 
- Despite this large collection of packages, it is still small compared to the over *150,000* packages available on PyPI.
***

## Miniconda
- Miniconda is a free minimal installer for conda. 
- It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages, including pip, zlib and a few others. 
***

## References
- [A gallery of interesting Jupyter Notebooks](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks)
- [When not use jupyter](https://thuijskens.github.io/2018/11/13/useful-code-is-production-code/)
- [CS197 Harvard: AI Research Experiences](https://docs.google.com/document/d/1z5ELxpTw_U01jUB6-D6ILqHRPg6SSiLE7VFQryH3LPU/edit#)
