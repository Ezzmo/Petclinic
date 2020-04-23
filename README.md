# QACFinalProject

## Contents 
* [Introduction](#Introduction) 
* [Deployment Pipeline](#pipeline) 
* [Deployment Pretequisites](#prerequisites)
* [Planning](#planning)
* [Use Cases](#UserCases)
* [Risk Analysis](#Risk) 
* [Technologies Used](#Technology) 
* [Environments ](#Environments)
* [Testing](#Testing)
* [Deployment](#Deployment)
* [Costs](#Costs) 
* [Project Conclusion](#Conclusion) 
* [Future Work](#FutureWork) 


<a name="Introduction"></a>
## Introduction 
### Project Brief
The general outline of this project was to use all the concepts from previous training modules to plan, design and implement a solution for automating the deployments and development workflows for the projects that are linked below: 
 
**Frontend client using AngularJS** https://github.com/spring-petclinic/spring-petclinic-angular
 
 **API using Java** https://github.com/spring-petclinic/spring-petclinic-rest
 

 
As a group of 4 individuals we would have to either use the tools we had been taught during our training such as **Terraform, Kubernetes, Ansible** or utilise other tools that would work in a similar fashion to these justifying why they would be the most preferable for deployment. 

The deployment of this project would require automated building and re-deployment to testing and live environments upon any GitHub changes, whilst also keeping track of running costs.   

<a name="pipeline"></a>
## Deployment Pipeline
![s5](/Documentation/Pipeline.jpg)

<a name="prerequisites"></a>
## Deployment Prerequisites

<a name="planning"></a>
## Planning

As this is a group project composed of 4 members, there will need to be adequate planning measures in place so that all individuals can work efficiently and coherently towards the main goal which is the successful deployment of the application.  

Therefore, throughout the duration of this project we chose to employ **Scrum** as our project management framework. Unlike conventional methods of project planning, Scrum promotes and encourages teams to learn through experiences, self-organise and share ideas whilst working towards resolving a problem.

![Planning](https://github.com/Ezzmo/Petclinic/blob/master/Documentation/Scrum%20Sprints.PNG)

This short video further explains the benifits of using **SCRUM**
[![Scrum Link](https://github.com/zReginaldo/MySQLdb/blob/master/Document/youtube-logo-png-46031.png)](https://www.youtube.com/watch?v=2Vt7Ik8Ublw) 

### Group member roles: 

### Product owner 
Our Trainer Jay Grindrod 

### Team members
https://github.com/AlinaDenisaB

https://github.com/Ezzmo

https://github.com/code-wizard91

### Scrum Master 
 https://github.com/zReginaldo



<a name="UserCases"></a>
## User Cases
![UserCases](https://github.com/Ezzmo/Petclinic/blob/master/Documentation/UserStories.PNG)

<a name="Risk"></a>
## Risk Analysis
![RiskAssessment](https://github.com/Ezzmo/Petclinic/blob/develop/Documentation/RiskAssessment.PNG)


<a name="Technology"></a>
## Technologies Used
![TechnologiesUsed](https://github.com/Ezzmo/Petclinic/blob/develop/Documentation/TechnologiesUsed.png)

<a name="Environments"></a>
## Environments
In this project we used multiple environments and tools to test build and deploy the applications, the tools are listed below:

- Terraform

Terraform was used to create our deployment infrastructure as code, in this case to create two environements; Staging and Production. In Terrafform each environment is identical but is tagged as Production and Staging. The environments have 1 Kubernetes Cluster and all it dependencies, 1 VM for controlling the clusters using Kubectl and testing the app and finally a Jenkins CI/CD server which executes the pipeline by building, testing and deploying the application on the K8 cluster.

We chose Terraform as it lets you write infrastructure as code, the infrastructure configurations can be versioned and maintained, so if another environment needs to be created, you can be sure that you are using the latest configurations which avoids environment drift.

- Ansible

Ansible was used to provision and configure the dependencies required to test and build our application on our remote hosts, this was done so that our app could be deployed seamlessly with Jenkins. We created multiple custom roles inside Ansible to install Docker, Install the applications our app needs to work, configure jenkins and more.


- Kubernetes


<a name="Testing"></a>
## Testing
![Testing](https://github.com/Ezzmo/Petclinic/blob/master/Documentation/Testing.PNG)

<a name="Deployment"></a>
## Deployment


<a name="Costs"></a>
## Costs
![Costs](https://github.com/Ezzmo/Petclinic/blob/develop/Documentation/Costs.PNG)


<a name="Conclusion"></a>
## Project Conclusion


<a name="FutureWork"></a>
## Future Work

