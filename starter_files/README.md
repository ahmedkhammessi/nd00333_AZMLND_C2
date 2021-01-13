# Operationalising ML Pipeline
This project comes as an important milestone of the udacity Azure ML nanodegree path, Tackling essentialy the Machine Learning Operations. The main goal of the ML model is to predict the clients that will be mostly engaged by a marketing campaign for the bank. On the techincal side of things, I will start by uploading the dataset, Create the experiment and get the best model, finally create and publish a pipeline.

During this project, The Auto ML experiment will be using classication to predict the value of the class 'Y' refering to being a potential client or not.

## Architectural Diagram
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/architecture.jpg)

## Key Steps
**1- Upload Bank Marketing Dataset**

During this initialization step, We will upload the dataset that the experiment will run against.
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/registered_dataset1.PNG)
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/registered_dataset.PNG)

**2- Create and Execute an Auto ML Experiment**

To prepare for this step the creation of the compute cluster is needed. We see the result of running the experiment using Classification.
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/completed_experiment.PNG)

**3- Verify the best model**

The result of running the experiment comes down to fing the best model as shown in the screenshot. This atually shows that the "VotingEnsemble" algorythme has been found to the best model with an accuray level of 0.19806

![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/best_model.PNG)

**4- Deploy the best model and enable Application Insights**

Although enabling the Application insights can be done within the previous step already, It's allways good to have the script option like shown here. Having application insights enabled is crutial on the long for debuging and error tracing.

![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/endpoint-appinsights-logs.PNG)

Here we can see that the Application Insights has been enabled and the model has been deployed successfuly.
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/applicationinsights-enabled.PNG)

**5- Run Swagger**

Azure ML studio provides the Swagger JSON file that we downloaded and expored by running swagger from a docker container on our local machine. Swagger is an Interface Description Language for describing RESTful APIs expressed using JSON and it comes really handy automated documentation, code generation, and test-case generation.

![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/swagger_screenshot1.PNG)
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/swagger_screenshot2.PNG)

**6- Consume the deployed model**

During this step, We will interact with the deployed model via HTTP requests and to do that the first step is to actually grab the URL and the primary key form the deployed model. A JSON document will be passed on to the HTTP REST API endpoint of the deployed model, the model processes it and send back the results.

![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/endpoint-script-screenshot1.PNG)
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/endpoint-script-screenshot2.PNG)

**7- Create the pipeline**

We reach the step of creating an automated pipeline, The Jupyter notebook need to be uploaded and ran all the cells after entering the correct values to the placeholders

![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/pipleine-created.PNG)

Run Details Widget in the Jupyter Notebook provides details such as run logs, duration, steps
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/rundetails_showdetails.PNG)

**8- Publish the pipeline**

The Azure ML studio provides a section to list the available pipline and that's where we can publish the endpoint with the trained model from the completed run.

![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/pipline-dataset-model.PNG)

It take a while to transit to the active state
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/pipline-dataset-model.PNG)

**9- Consume the pipeline**

Once published we can authenticated and retrieve the endpoint URL to communicate via http request or the SDK.

![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/pipline-restendpoint-publish.PNG)
![alt text](https://github.com/ahmedkhammessi/nd00333_AZMLND_C2/blob/master/pipline-active.PNG)

## Screen Recording
https://youtu.be/f7XMSWWDDX4

## Improvements

In general the current specifics of the Auto ML experiment are decent since we've got a high accuracy level 0.94796 , Nevertheless we can improve by using the deeplearning mechanisme and for that we will need to increase the allowed run duration and the compute power to get faster results. 
