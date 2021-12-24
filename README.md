# Overview

As part of the Udacity Azure Devops Nano Degree, This is the second project 'Building a CI/CD Pipeline'. 
In this project, we will be doing the below tasks
Create a GitHub repository and integrate it to the Azure
Deploy the app in Azure CloudShell
Deploy the app as an Azure App Service
GitHub Action along with Azure Devops Pipeline to trigger CI/ CD when any commit is made to the Repo.

## Project Plan
<TODO: Project Plan

* [Trello board](https://trello.com/b/j7XvQMlY/azure-proj-2) link used for tracking the project.
* [Spreadsheet](https://github.com/ChinmaiCharan/AzureDevopsProj2/files/7774851/project-management-template.xlsx) that contains the project time line.

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

Create GitHub Action
![Github Action](https://user-images.githubusercontent.com/95535252/147286406-35e15490-df9b-4989-a251-0db900d8a7bd.JPG)

* Project running on Azure App Service
Create an App Service in Azure.


Our App Service is called proj2cicd and the resource group is called proj2rg:

az webapp up -n proj2cicd -g proj2rg
![image](https://user-images.githubusercontent.com/95535252/147284016-6181d4be-12ed-4186-91ad-62e1288b796c.png)

webapp infrastructure is created and verify the frontend:
![image](https://user-images.githubusercontent.com/95535252/147285263-27a24129-fcbd-4392-9bca-1cf339082dfb.png)


* Passing tests that are displayed after running the `make all` command from the `Makefile`

* Output of a test run

* Successful deploy of the project in Azure Pipelines.  (https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops).

Next, create the pipeline in Azure DevOps. More information on this process can be found here. The basic steps to set up the pipeline are:

Go to https://dev.azure.com and sign in.
Create a new private project.
Under Project Settings create a new service connection to Azure Resource Manager, scoped to your subscription and resource group
![image](https://user-images.githubusercontent.com/95535252/147286650-2794a94c-067f-493b-b8a7-d8bda096617d.png)

Create a new pipeline linked to your GitHub repo.
![image](https://user-images.githubusercontent.com/95535252/147286879-0a0a0ac6-a3db-4a15-9d32-634a2a5db970.png)

To test the app running in Azure App Service, edit line 28 of the make_predict_azure_app.sh script with the DNS name of your app. Then run the script:

./make_predict_azure_app.sh 
![image](https://user-images.githubusercontent.com/95535252/147288231-5a8d50cd-6260-47a3-bf5f-7c06b5b50bb9.png)

![image](https://user-images.githubusercontent.com/95535252/147288299-583f26dd-f609-4bae-97e3-4b7fe0ecc339.png)


![image](https://user-images.githubusercontent.com/95535252/147288556-5b04d576-efee-4c00-b13d-cc4ae05afd45.png)



Load testing
We can use locust to do a load test against our application. In this example we will do a load test against the app running locally rather than in Azure.

Install locust:

pip install locust
Ensure the app is running:

python app.py
![image](https://user-images.githubusercontent.com/95535252/147288676-86b6c02d-786f-4178-8044-e205fdb41361.png)

Start locust:
![image](https://user-images.githubusercontent.com/95535252/147288723-8221d284-a3c5-4c09-8f7a-14dd6feeb1af.png)


locust
Open a browser and go to http://localhost:8089. Enter the total number of users to simulate, spawn rate, set the host to localhost:5000, and click Start Swarming:
![image](https://user-images.githubusercontent.com/95535252/147289030-f4a84d9e-0e74-4eb3-af0f-51ac7bfc3c25.png)

![image](https://user-images.githubusercontent.com/95535252/147288975-31ced630-a89f-4db5-89a1-246cccb3c7ba.png)
![image](https://user-images.githubusercontent.com/95535252/147288992-f9010834-5df9-431e-a168-41f0cda608a1.png)

## Enhancements

Currently, there is only a single branch in GitHub. In the future it would be good to create multiple branches, so code can initially be tested and deployed in a staging environment. If it works correctly in the staging environment the changes could then be merged into the production branch and the code deployed into the production environment.

## Demo 

<TODO: Add link Screencast on YouTube>


