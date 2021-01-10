# Machine Learning Operation

### In this project we are operationalizing Machine Learning tasks. Determing best models with an auto ml run and an an auto ml pipeline using python.

## Overview

We have performed two different tasks in this project:
1. Best Model Deployment in Azure ML Studio using Auto ML:
  Steps -
  - We started by creating a new auto ml run.
  - Then we registered the bankmarketing dataset. According to UCI repository, this data is related with direct marketing campaigns of a Portuguese banking   institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed. We seek to predict whether or not the potential client would accept to make a term deposit with the bank.
  - After, we configured auto ml run for 'classification' in Azure ML studio.
  - The model ran a bunch of algorithms and returned VotingEnsemble as the bets model with the most accuracy of 92%.
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
 
 
 
