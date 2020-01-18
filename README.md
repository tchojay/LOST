
# Hackaotearoa Length of stay Team (LOST) 

This repo contain codes for calculating Length of Stay in Intensive Care Unit (ICU). This repo is created as a part of HACKATHON event of the http://hackaotearoa.co.nz/

### CONTENTS
1. LOST Team Members
2. GETTING STARTED
3. DOCUMENTATION
4. DB on BigQuery
5. Analyzing Data with Google Colab


### 1. LOST TEAM MEMBERS
1. Tshewang Chojay, DITT, Bhutan
2. Thinley Dorji, MoIC, Bhutan
3. Jacob Han, NZ Airlines, NZ
4. Steven Yoo, UoA, NZ
5. Renfei Ma, UoA, NZ

### 2. GETTING STARTED

The datasets are hosted on Google Cloud, which requires a Gmail account to manage permissions.

Create a Gmail account, if you don't already have one. It will be used to manage your access to the resources.
Give your gmail address to the session hosts. You need to be approved by the administrator to have access to the data. 

### 3. DOCUMENTATION
eICU Collaborative Research Database: https://eicu-crd.mit.edu/ 

### 4. Databases on BigQuery
BigQuery is a database system that makes it easy to explore data with Structured Query Language ("SQL"). There are several datasets on BigQuery available for you to explore, including eicu_crd (the eICU Collaborative Research Database).

You will also find "derived" databases, which include tables derived from the original data using the code in the eICU code repositories.

#### Open BigQuery.

At the top of the console, select hack-aotearoa as the project. This indicates the account used for billing.

"Pin" a project to the resources menu to view available datasets. In the Resources menu on the left, click "Add data", "Pin a project", then add the following project names: physionet-data and hack-aotearoa.

You should be able preview the data available on these projects using the graphical interface.

Now try running a query. For example, try counting the number of rows in the demo eICU patient table:
```
SELECT count(*)
FROM `physionet-data.eicu_crd_demo.patient` 

```

### 4. Analysing data with Google Colab
Python is an increasingly popular programming language for analysing data. We will explore the data using Python notebooks, which allow code and text to be combined into executable documents. First, try opening a blank document using the link below:

https://colab.research.google.com/


### 5. PREDICTIONS

## 5.1 LOADING LIBRARIES & CONNECTING TO DB
```
# Import libraries
import os
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# model building
from sklearn import ensemble, impute, metrics, preprocessing, tree
from sklearn.model_selection import cross_val_score, train_test_split
from sklearn.pipeline import Pipeline

# Make pandas dataframes prettier
from IPython.display import display, HTML, Image
plt.rcParams.update({'font.size': 20})
%matplotlib inline
plt.style.use('ggplot')

# Access data using Google BigQuery.
from google.colab import auth
from google.cloud import bigquery

```

```
# authenticate
auth.authenticate_user()
```
```
# Set up environment variables
project_id='aarhus-critical-2019-team'
os.environ["GOOGLE_CLOUD_PROJECT"]=project_id

```




