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
The diagram below shows the operations done in the project from the start to finish.
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. 

## Key Steps

# Automated ML Experiment
In this step, we first upload our dataset using the dataset's URL:
![Dataset](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/Registered%20data%20sets.PNG)  

Then we use this data to create an AutoML run to determine the best model:
![Complete Run](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/complete%20run.PNG)  

After the run is complete, we're able to determine the best model which is the **Voting Ensemble** with accuracy of **0.91866**:
![Best Model](https://github.com/dinaabdulrasoul/Operationalizing-Machine-Learning/blob/main/screenshots/best%20model.PNG)  
## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
