# Getting started with conda package manager


## 1. Create environment:-
`% conda create --name conda-env python                  # Or use -n`
(goes in the /home/user/miniconda3/envs directory)
> or create environment in a specified path:-
`% conda create --prefix /path/to/conda-env             # Or use -p`


## 2. Different version:-
`% conda create -n conda-env python=3.7`


## 3. Preloaded packages:-
`% conda create -n conda-env numpy requests`
> and their versions if needed:-
`% conda create -n conda-env python=3.7 numpy=1.16.1 requests=2.19.1`


#### Note: It’s recommended to install all the packages you want to include in an environment at the same time to help avoid dependency conflicts.


## 4. Activate environment:-
`% conda activate conda-env`


## 5. Deactivate environment:-
`% conda deactivate`


## 6. List environments:-
`% conda env list`
> or
`% conda info --envs`


## 7. Install packages:-
> a)From inside an active environment.
`(conda-env) % conda install pandas=0.24.1`
Set default channel to `conda-forge`\
`conda config --add channels conda-forge`\
`conda config --set channel_priority strict`\
`conda install <package-name>`

> b)From your default shell.
`% conda install -n conda-env pandas=0.24.1      # Or -p /path/to/env`


## 8. Update Packages:-
> a) `(conda-env) % conda update pandas`
> b) `% conda update -n conda-env pandas             # Or -p /path/to/env`


## 9. List Packages:-
> a) `conda list`
> b) `% conda list -n conda-env                      # Or -p /path/to/env`


## 10. Install package from other conda repositories:-
> (installing opencv from Conda-Forge)
`(conda-env) % conda install --channel conda-forge opencv     # Or -c`
`(conda-env) % conda list`


## 11. Add a channel permanently as package source:-
`% conda config --append channels conda-forge`


## 12. Install packages from PyPI:-
`(conda-env) % pip install requests`
`(conda-env) % conda list`


## 13. Environment Files:-
> a) `(conda-env) % conda env export --file environment.yml       # Or -f`
> b) `% conda env export -n conda-env -f /path/to/environment.yml`
#### This will generate environment files


## 14. Duplicating Environments:-
> (Given an environment.yml file, you can easily recreate an environment.)
`% conda env create -n conda-env -f /path/to/environment.yml`
> or (add the packages listed in an environment.yml file to an existing environment)
`% conda env update -n conda-env -f /path/to/environment.yml`


## 15. Conda Revisions:-
> list revisions
`(conda-env) % conda list --revisions`
> rollback to revision 1
`(conda-env) % conda install --revision 1`
> list revisions (Showing latest only)
`(conda-env) % conda list --revisions`
#### The — signs by each package tell us we’ve successfully removed them from our environment.


## 16. Environments With R:-
`(conda-env) % conda install r-base`
> or do this while creating an environment
`% conda create -n r-env r-base`

#### Conda’s R packages are available from the R channel of Anaconda Cloud, which is included by default in Conda’s default_channels list, so you don’t need to specify the R channel when installing R packages like, say, tidyverse.
`% conda activate r-env`
`(r-env) % conda install r-tidyverse`
#### Note: All packages from the R channel are prefixed with “r-".

#### If you want, you can install the r-essentials bundle, which includes over 80 of the most popular scientific R packages, like tidyverse and shiny.
`(r-env) % conda install r-essentials`
#### Last, if you want to install an R package that Conda doesn’t offer, you’ll need to build the package from CRAN, instructions to which you can find here.




# Bonus (Installation configuration with custom shell -> zsh)

## 1. Export Path:-
`export PATH="$HOME/anaconda3/bin:$PATH"`

## 2. Initialize for zsh:-
`conda init zsh`
#### Now restart shell.




# References
==========================


https://towardsdatascience.com/a-guide-to-conda-environments-bc6180fc533
https://stackoverflow.com/questions/31615322/zsh-conda-pip-installs-command-not-found
