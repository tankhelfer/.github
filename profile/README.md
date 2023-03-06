# Tankhelfer

Tankhelfer is a optimization and modelling project which should help you to find the best gas station by price on a route.

In this repository you can find all services.

You can find the according setup instructions in the README-files inside the service-folders.

1. [Project Structure](#1-project-structure)
2. [Optimization Service](#2-optimization-service)
3. [History Database](#3-database)
4. [Modelling Service](#4-modelling-service)
5. [Research Service 1](#5-research-service-1)

## 1. Project Structure
-----------------------
```
                                           ______________________
                                          |                      |
                                         DB  tankhelfer-history  |
                                          | /                  \ |
backend-service --- optimization-service ---                    --- modelling-service  
                                          | \                  / |
                                          |  tankhelfer-future   |
                                          |                      |
                                           ‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾
```


## 2. Optimization Service
--------------------------

service description

## 3. Database
--------------
In the History Database the history datadumps from [Tankerkönig](https://creativecommons.tankerkoenig.de) are stored.
This dump contains all the information of the gas stations in Germany from fall 2020 until end of February 2023.
There are two Tables: one containing details about the gas stations, one containing the price updates.

The history data is used for research purposes on price forecasting and contains real prices. Once Tankhelfer is in production, this database gets updated with real time data.

Currently, we are also using this database for our gas station optimizer.

## 4. Modelling Service
-----------------------

service description

## 5. Research Service 1
------------------------

The goal of this research service is to analyse the history data and find structures in the data. 


# Setup Instructions

Please use each service seperately with seperate virtual environments to avoid loading unnecessary libraries. 

The following instructions should help you by dealing with virtual environments.

## Virtual Environments

### Ceate a virtual environment

To create a virtual environment `cd` to the correct service repository and run
```
python -m venv .venv
```

### Choose virtual environment as python interpreter

Run
```
source .venv/bin/activate
```

### Install requirements

To install the requirements from the [requirements.txt](optimization-service/requirements.txt) (e.g. for the optimization service)
```
pip install -r requirements.txt
```

### Update requirements file

To document your requirements, please don't forget to update the requirements by running
```
pip freeze > requirements.txt
```

## Handling secrets

To exchange secrets, passwords and other login data please create a `.env` file in each service repository. Furthermore add this file to your `.gitignore`

## Gitignore

As we don't want to store secrets and specific python setups in our github repository, please create a `.gitignore` to every service repository. E.g. 

```
# filename: .gitignore 

.env
.venv
```
