# Jupyter-Notebooks

## What is Jypter?
- Jupyter is a web application that allows you to display and execute Python interactively. The interface is writteni n CSS, HTML and JavaScript. This run in a web browser on the client machine.

## Installation
- It can be installed via pip as: `pip insta;; jupyter`
- To see which jupter is being used use: `which jupyter`
- To launch Jupyter type: `jupyter notebook`

## How to create a virtual environment with conda
- See which conda you are using (meaning it shows the path of the executable being called): `which conda`
- Create a virtual environment using conda specific command: `conda create –-name my_env_name python=3.7` 
- Activate the virtual environment: `conda activate my_env_name` 
- How to visualise all the env available: `conda env list`
- Install any package you like via these two options: `conda install package_name` or `pip package_name`
- How to delete a virtual env: `conda env remove --name=my_env_name`

## How to manage python packages
- Update a to a specific module version: `scikit-learn==0.24.1 –upgrade`
- How to revert to an older version: first `pip uninstall scikit-learn` then `pip install scikit-learn==0.18.2`

# How to run a specific environment within your jupyter notebook
- All command lines were taken form this [Ref#1](https://medium.com/@nrk25693/how-to-add-your-conda-environment-to-your-jupyter-notebook-in-just-4-steps-abeab8b8d084) and [Ref#2](https://janakiev.com/blog/jupyter-virtual-envs/)
- Let us assume we have a number of different virtual environments in our machine and we’d like to remind ourself what these are. Type on the console: `conda env list` and hopefully more than one virt env will be shown. Now let us assume I'd like to use one of them in my Jupyter notebook.
- Before doing anything activate your virtual environment: `conda activate my_specific_virt_env_name`
- We need `ipykernel` which is installed using this command: `conda install -c anaconda ipykernel`
- After installing this, type: `python -m ipykernel install --user --name=my_specific_virt_env_name`
- Now your new env will be shown in the drop down menu under `New`.

![image](https://user-images.githubusercontent.com/89139139/150124430-456ce370-12ca-4eab-8504-cefeda2e8194.png)




