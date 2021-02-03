# Managing the end-to-end machine learning lifecycle with MLFlow in Azure

This Repository contains the resources for MLFlow deployment with Azure resources

# Basic setup

## Clone This Repository
  - `git clone git@github.com:franklin8705/MLFlow-In-Azure.git`

## Install Dependencies
- **with virtualenv**
  - install virtualenv: `pip install virtualenv`
  - create a new environment: `virtualenv mlflow_tutorial`
  - activate the environment: `source /mlflow_tutorial/bin/activate`
  - run `pip install -r requirements.txt`

- **with anaconda**
  - install virtualenv: `pip install anaconda`
  - create a new environment: `conda create -n mlflow_tutorial`
  - activate the environment: `conda activate mlflow_tutorial`
  - install pip in the environment: `conda install pip`
  - run `pip install -r requirements.txt`

## The notebooks
- `hands_on_example local.ipynb`
- `hands_on_example Azure Resources.ipynb`
- `hands_on_example AML.ipynb`
- `hands_on_example Azure Databricks.ipynb`
- `Create AzureML Workspace Template`
- run `jupyter notebook`


# Setup the Data environment

## Create Local Environment Variable File (root/.env)
## Update connection string information 
- Simple examples:
  - `export MLFLOW_SERVER_URI = '<mlflow_uri>`
  - `export AZURE_SUBSCRIPTION_ID = '<subscription>`
  - `export AZURE_RESOURCE_GROUP = '<resource_group>`
  - `export AZURE_TENANT_ID = '<tenant_id>`
- For more complex examples:
  - `export BLOB_ACCESS_KEY = '<Azure storage access key>`
  - `export BLOB_CONNECTION_STRING = '<Azure storage connection string>`
  - `export PG_SERVER_HOST = '<host_url>`
  - `export PG_DBNAME = '<dbname>`
  - `export PG_USER = '<user name>`
  - `export PG_USER_PASSWORD = '<password>`
- Note: this file is included in the `.gitignore`

## Create Azure Postgres DB Instance
- www.portal.azure.com

## Test connection with the database
- set up environment vars (.env)
- map env vars with settings.py
- run `connect_db.py`

## Set up local environment vars to connect to blob
- `export AZURE_STORAGE_ACCESS_KEY = '<access key>`'
- `export AZURE_STORAGE_CONNECTION_STRING = '<connection string>`'

## To Start Tracking Server
- `mlflow server \`
    `--backend-store-uri /mnt/persistent-disk \`
    `--default-artifact-root blob://my-mlflow-blob/ \`
    `--host 0.0.0.0`
    `--port 5000`

