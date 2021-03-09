# Project Specific environment.yml file:
![cyrus_its_customized](https://media.giphy.com/media/9fvhbT2qUPYqH9n14j/giphy.gif)
> Up until now, your projects have most likely not included custom .yml files.  You likely have used the same learn-env that you use for following along with lessons found [here](https://github.com/learn-co-curriculum/dsc-data-science-env-config.git). The learn-env contains a lot of extra libraries which will not be used in the Phase 3 project, like pyspark, keras, and surprise.  You will most likely also install new packages, such as geopandas or psycopg2. Ideally, your final repo should have a .yml file which includes only the packages which are necessary to run replicate your work. 

> You can build your .yml file as you go, or at the end.  For this exercise, we will assume that you have already finished your project using the learn-env. We will use the index.ipynb as our guide to creating a lighter-weight .yml.

> There are a bunch of conda commands, some of which are difficult to remember.  If you forget a command, the [conda docs](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) will come in handy.
## Conda Create 

> Open up a fresh terminal, and navigate to where you cloned this repo.  cd into the virtual_envs directory.  
> Deactivate any environment currently running.   

  >> `conda deactivate`  

> The beginning of your terminal prompt should reflect the change.  Probably it changed from (learn-env) to (base).  
> Create a new conda environment with a name associated with your project.  
>> `conda create --name classification`  

> If you run `conda info --envs` you will see all your conda environments, including the new one.  

> With your new environment active, `run conda list`.  You will not have any packages installed.   
> Notice also that if you run `python --version`, no version shows up.  Python has not been installed.  We could have installed a Python version when we created the environment:
>> `conda create -name python=3.8.5`

> The version above is the one included with learn-env. 

## Package Installations
> Starting from a finished product, we will want to open up our project files and make sure all the dependencies are included in the .yml.  (If you are creating the yml as you go, install the packages as you use them).  The first thing to do will be to open a notebook, but jupyter has not yet been in installed.  Let's install it.

### Search
> If you are unsure of a package name, you can search the packages conda maintains using: `conda search jupyter`
> In this case, the package names are juypter and jupyterlab.

## Install jupyter/jupyterlab
> Run:
>>`conda install jupyter`

> And if you want:

>>`conda install jupyterlab`

## Install the ipykernel
> In order to make the new environment available to the Jupyter server, we need to install the kernel.  With your environment running, after replacing the filler text with your environment name, run the following line.

>> python -m ipykernel install --user --name <environment_name_here> --display-name "display_name_here"

> Filled in:
>> python -m ipykernel install --user --name classification --display-name "classification"

## Install Packages Needed to Run the Notebook
> Open up the jupyter notebook in the folder.

> Make sure your environment is available under the dropdown menu.  

> Start running the cells. Every time a "No Module Named [...]" error is thrown, return to the terminal and conda install that package.

## Creating the .yml file
> Once all of the packages necessary to run all of the code in your project repository has been installed, it is time to make your environment.yml.  

>> conda env export > environment.yml
