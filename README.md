# Overview

This is my submission for the 'Building a CI/CD Pipeline' project as part of the 'DevOps Engineer for Microsoft Azure' nanodegree program from Udacity.

This project contains a python application that is designed to predict housing prices in Boston (I did not create the python app myself). This repo will enable you to:

Deploy the app in Azure CloudShell
Deploy the app as an Azure App Service
Any commits to the GitHub repo trigger automated code testing using GitHub Actions. A pipeline has been created in Azure DevOps, and the updated code is also automatically tested in Azure DevOps and deployed to the Azure App Service.

## Project Plan
<TODO: Project Plan

* A link to a Trello board for the project
* A link to a spreadsheet that includes the original and final project plan>

## Instructions
* Architectural Diagram
![architecture](https://user-images.githubusercontent.com/95535252/147277332-0ebd5f83-7d24-432b-8408-e439d75a0abb.jpg)

Instructions for running the Python project.  

* Project cloned into Azure Cloud Shell

  Open Azure Cloud Shell, create a SSH key pair by running the command : ssh-keygen -t rsa;
  
  Copy the public SSH key generated using command : (e.g., the file ~/.ssh/id_rsa.pub);
  ![rsa_pub](https://user-images.githubusercontent.com/95535252/147278056-bd402a95-9d3e-473d-ad57-5f2e0ecf9f5d.JPG)
  
  Add the SSH key on to the GitHub
  ![image](https://user-images.githubusercontent.com/95535252/147277272-d439ae37-9a93-4888-99e5-52b17ab6d00e.png) 

  Run git clone git@github.com:ChinmaiCharan/AzureDecopsProj2.git to clone the repository into Azure Cloud Shell:
  ![Uploading AZ Cli Cone.JPG…]()

  Create and activate the virtual environment:

  source ~/.udacity-devops/bin/activate
  Install dependencies in the virtual environment and run tests:

  make all  

  ![make all](https://user-images.githubusercontent.com/95535252/147281007-8838ba0d-d489-463e-843f-6bb145ed7285.jpg)

  Start the application in the local environment:
  
  python app.py
  
  ![image](https://user-images.githubusercontent.com/95535252/147283414-c9ce9507-08e0-4355-b098-8c0ab2829ed4.png)
  
   Open a separate Cloud Shell and test that the app is working:

./make_prediction.sh
![image](https://user-images.githubusercontent.com/95535252/147283768-97bb0c4b-4179-4dfd-8c4a-18023f1b47e4.png)


* Project running on Azure App Service
Create an App Service in Azure. 
Our App Service is called proj2cicd and the resource group is called proj2rg:

az webapp up -n proj2cicd -g proj2rg
![image](https://user-images.githubusercontent.com/95535252/147284016-6181d4be-12ed-4186-91ad-62e1288b796c.png)

webapp infrastructure is created and verify the frontend:
![image](https://user-images.githubusercontent.com/95535252/147285263-27a24129-fcbd-4392-9bca-1cf339082dfb.png)


* Passing tests that are displayed after running the `make all` command from the `Makefile`

* Output of a test run

* Successful deploy of the project in Azure Pipelines.  [Note the official documentation should be referred to and double checked as you setup CI/CD](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops).

* Running Azure App Service from Azure Pipelines automatic deployment

* Successful prediction from deployed flask app in Azure Cloud Shell.  [Use this file as a template for the deployed prediction](https://github.com/udacity/nd082-Azure-Cloud-DevOps-Starter-Code/blob/master/C2-AgileDevelopmentwithAzure/project/starter_files/flask-sklearn/make_predict_azure_app.sh).
The output should look similar to this:

```bash
udacity@Azure:~$ ./make_predict_azure_app.sh
Port: 443
{"prediction":[20.35373177134412]}
```

* Output of streamed log files from deployed application

> 

## Enhancements

<TODO: A short description of how to improve the project in the future>

## Demo 

<TODO: Add link Screencast on YouTube>


