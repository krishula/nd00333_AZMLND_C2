# Machine Learning Operation

### In this project we are operationalizing Machine Learning tasks. Determing best models with an auto ml run and an an auto ml pipeline using python.

## Overview

We have performed two different tasks in this project:
1. Best Model Deployment in Azure ML Studio using Auto ML:
  Steps -
  - We started by creating a new auto ml run.
  - Then we registered the bankmarketing dataset. According to UCI repository, this data is related with direct marketing campaigns of a Portuguese banking   institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed. We seek to predict whether or not the potential client would accept to make a term deposit with the bank.
  - After, we configured auto ml run for 'classification' in Azure ML studio.
  - The model ran a bunch of algorithms and returned VotingEnsemble as the best model with the most accuracy of 92%.
  - We chose the best model and deployed it, which created a REST endpoint. Application insights was enabled, Swagger documentation was produced and we concluded by benchmarking the REST endpoint.
  - We consumed the REST endpoint, by sending the json requests to the REST endpoint and got predictions back.
  
2. Published ML Pipeline using Azure ML SDK:
  Steps -
  - We initialized the Workspace and reload the Experiment, the cluster and the Dataset from the first task (Auto ML run above).
  - We configured automl pipeline and PipelineData for the metrics output and the best model output of the pipeline.
  - We created and sublmitted the pipeline for run.
  - After the run is complete we fetch the metrics of the best model and other child runs.
  - We published the pipeline in order to rerun it via the REST endpoint on the test data.
 
 ## Architectural Diagram
 
 ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Screen%20Shot%202021-01-09%20at%208.56.02%20PM.png)
 
 ## Future Improvements
 
 I think we can make this model better with adding deep learning to it. Also, a bigger dataset with more number of rows might help achieve more accuracy.
 
 ## Screenshots of Main Steps
 
 ### Auto ML Run, Best Model and Endpoints
 
  - Registered Dataset:
 
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Registered%20Dataset.png)
 
  - Auto ML Run Compeletion:
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Run%20Completed.png)
  
  - Best Model Details
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Best%20Auto%20ML%20Model%20Deploy.png)
  
  - Best Model Deploy Details - Applications Insight Enabled
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Best%20Model%20Deploy%20Details.png)
  
  - running logs.py part1
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/logs1.png)
  
  - running logs.py part2
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/logs2.png)
  
  - running logs.py part3
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/logs3.png)
  
  - We hit the "Swagger URI" in the deployed model(as seen in the first of the previous 4 images). From there we downloaded the swagger.json and placed it in the "swagger" folder and ran swagger.sh (on port 9000 since we didn't have permission on port 80) and the serve.py (on port 8000).
  Aftermath of that is in the below few screenshots:
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/swagger1.png)
  
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Swagger2.png)
  
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Swagger3.png)
  
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Swagger4.png)
  
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Swagger5.png)
  
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Swagger6.png)
  
  - Consume Model Endpoints
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/endpoints1.png)
  
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/endpoints2.png)
  
  ### Publish Pipeline with Azure ML SDK
  
  - Below is a screenshot after we created the pipeline from the Azure SDK using the "aml-pipelines-with-automated-machine-learning-step.ipynb" notebook:
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Pipeline%20Creation%20using%20Azure%20ML%20SDK.png)
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Pipeline%20Endpoints.png)
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Dataset.png)
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Published%20Pipeline%20Overview.png)
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Run%20Details.png)
  
  ![alt text](https://github.com/krishula/nd00333_AZMLND_C2_Machine_Learning_Operations/blob/master/Screenshots/Experiments.png)
  
  ## Screencast
  
   - A screencast of a working deployed model endpoint, the deployed pipeline, the AutoML model  we have created can be found here:
  
  https://youtu.be/FXbGYujZ4Go
  
  
  
