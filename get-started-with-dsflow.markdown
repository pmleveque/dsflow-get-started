---
title: Get started with dsflow
date: 2017-11-17 12:35:00 Z
---

# dsflow

This project contains the codebase of the dsflow CLI and dsflow framework. Use this repo to install dsflow.


## dsflow quick start

### Install dsflow

#### Pre-requisites on Mac:

Brew and Python need to be installed on your system.
If not, execute in your terminal:

```
xcode-select --install
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install python
```

Docker also is needed:

```
brew cask install docker
```

Troubleshoot:  
If your xcode is outdated, update it with the app store, or move it to Trash.

Installation on Ubuntu: https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/

Installation on Windows:
https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/


#### [optional] install and use dsflow within a virtual environment:

```
pip install virtualenv
virtualenv ~/.venv-dsflow
source ~/.venv-dsflow/bin/activate

```

#### Eventually run the following to install dsflow CLI:

```
pip install -e git+https://github.com/pmleveque/dsflow-cli/#egg=DsflowAlpha
```

#### Check installation, running:

```
dsflow
```

#### [optional] if you use a virtual environment, add the following line to `~/.bash_profile`

```
alias dsf="source ~/.venv-dsflow/bin/activate"
```

Then, simply execute `dsf` to make activate dsflow.


### Create new dsflow project

Move to the directory where you want to create your project, and run:

```
dsflow new <PROJECT_NAME>
cd <PROJECT_NAME>
```



### Create first flow (notebook-based)

Will start the processing of a CSV file.

1. Then run:  
`$ dsflow generate [TEMPLATE_NAME] [FLOW_NAME]`  
For instance:
`$ dsflow generate from_csv departements`

1. (optional) place your csv file into the datastore.  
IMPORTANT: The datastore follows precise conventions:   `/datastore/raw/<DATASET_NAME>/ds=<YYYY-MM-DD>/`  
For instance: `/datastore/raw/departements/ds=2017-08-02/`

1. Then launch python IDE (JupyterLab):  
`$ dsflow start`

1. Open browser and navigate to http://localhost:8888/  
(password is `green3`)

1. You can now open the notebook and start editing it.




### Exit IDE

`$ dsflow stop`