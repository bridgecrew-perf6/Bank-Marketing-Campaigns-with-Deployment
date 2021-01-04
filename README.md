# Operationalizing Machine Learning

## Table of Contents
* ### Overview
* ### Architectural Diagram
* ### Key Steps
     * Automated ML Experiment 
     * Deploy the best model
     * Enable App Insights & Logging
     * Swagger Documentation
     * Consume model endpoints
     * Create and publish a pipeline
* Screen Recording
* Standout Suggestions
* References

## Overview
This projects aims to create a cloud-based machine learning model for the Bank Marketing Dataset, which contains data about marketing campaigns for a bank, to create this model we will utilize the power of AutoML for this classification problem to be able to predict whether a bank product would be subscribed by the client or not.  
The project involves configuring, deploying and consuming the model.
The project also includes creating, consuming and publishing an ML Pipeline.

## Architectural Diagram
The diagram below illustrates the keys steps of our operation:
![Architecture](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/architecture%20diagram.PNG) 

* We use our dataset to create an AutoML run to find the best model to fit our data. 
* We use the model obtained and our data to train an ML pipeline.
* We publish both the model & pipeline to endpoints to be ready for consumption. 

## Key Steps

### Step 1: Automated ML Experiment
In this step, we first upload our dataset using the dataset's URI:
![Dataset](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/Registered%20data%20sets.PNG)  

Then we use this data to create an AutoML run to determine the best model:
![Complete Run](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/complete%20run.PNG)  

After the run is complete, we're able to determine the best model which is the **Voting Ensemble** with accuracy of **0.91866**:
![Best Model](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/best%20model.PNG)  

### Step 2: Deploy the best model
In this step, we deply the Voting Ensemble model using Azure Container Instacne (ACI) while making sure that the Authentication option enabled.
![Deployment](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/deploy.png)  


### Step 3: Enable App Insights & Logging
We enable the Application Insights by editing the logs.py script to match the deployed model ID and setting App Inights to ***True*** then we run the python script.
![App Insights](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/App%20insights%20enabled.PNG)  

Running logs.py after editing it:
![Logs](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/enabling%20logs.PNG) 

Screenshots of Logs:
![Logs](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/logs%201.PNG) 
![Logs](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/logs%202.PNG) 

### Step 4: Swagger Documentation
In this step we setup Swagger to be able to deploy and consume the model using Swagger.
We start by download the swagger.json file from our deployed model on Azure. Then we run swagger.sh and serve.py script on Powershell command window.
Swagger on localhost:  
![Swagger](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/swagger%20methods.PNG) 
![Swagger](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/swagger1.PNG) 
![Swagger](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/swagger2.PNG) 
![Swagger](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/swagger3.png) 

### Step 5: Consume model endpoints  
Using the endpoint.py script to consume the model endpoints, we first edit the *scoring_uri* and the *key* in the script to match the key for your service and the URI that was generated after deployment, then we execute endpoint.py script.
![Endpoint](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/endpoint.png) 

### Step 6: Create and publish a pipeline
In this step, we first update our jupyter notebook variables to match our environment. 
And finally we deploy our training pipeline and publish it. 

Here we can see the Pipeline section in Azure Machine Learning studio:
![Pipeline](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/pipeline%20section.PNG)

Pipeline Endpoint:
![Pipeline](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/pipeline%20endpoint.PNG) 

Bankingmarketing dataset with AutoML module:
![Pipeline](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/pipeline%20run.PNG) 

Published Pipeline Overview:
![Pipeline](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/active%20pipeline.PNG) 

Run Details Widget:
![Pipeline](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/run_widgets.PNG) 

![Pipeline](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/pipeline%202.PNG) 

## Screen Recording
[Screencast](https://www.youtube.com/watch?v=SZASW4ACtXY)

## Future Improvements
* We can increase the Exit Criterion time from 1 hour to the default value of 3 hours to be able to find models of higher accuracy.
* We can  enable Data drift tracking to ensure accuracy of the model.
