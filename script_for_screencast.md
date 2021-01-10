## Script for the project 2 screencast:

  - First screen shows all the experiments that are active at the moment. It includes the auto ml run that we created in task 1 from the documentation and the two runs for azure ml sdk pipeline (task 2); one for the train data and then the pipeline-rest-endpoint.
  - Then we select the experiment “auto-ml-project2” and see that the run has been completed. We can see the best model was “Voting Ensemble” with an accuracy of about 92%. We click the best model and now we can see that it has been successfully deployed. The state of deployment is healthy and we have successfully generated the swagger URI and Applications Insights are enabled. We choose the best model for deployment and enable "Authentication" while deploying the model using Azure Container Instance (ACI). The executed code in logs.py enables Application Insights. "Application Insights enabled" is disabled before executing logs.py.
  - After that we go to “Pipelines” and look at the “Run 1” for the azure ml sdk pipeline run. It’s been successfully completed. Similarly, we also check the run status of the experiment “pipeline-rest-endpoint”. "piepline-rest-endpoint" was created when we re-ran the model on our test data.
  - At the end, we go back to “Pipelines” and select the tab “Pipeline Endpoints”, where we can see the “Published pipeline overview” and its last run status being “Finished”.

Thank you!
