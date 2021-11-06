# DevOps and the Cloud 

DevOps and the cloud, although they are closely related but they are not the same thing.

**Devops** - It is a culture of collaboration between Development and Operations. And It can happen inside or outside of the cloud.

**Cloud** - It means remote servers on the internet that offer services in place of locally hosted solutions.

DevOps and the cloud developed alongside one another, and many cloud services are built on DevOps practices.

- **Infrastructure as a service (Iaas)** : Provides bare OS. You are responsible for all installation and configuration above the OS level.
  Example:-
  - Amazon EC2 instances
  - Microsoft Azure VMs and containers
  - Google Compute Engines

- **Platform as a service (Paas)** : provides ways to develop an app and use databases. Only responsible for managing apps and data.
  Example: 
  - AWS Elastic Beanstalk
  - Heroku
  - Google App Engine
  
- **Software as a service (Saas)** : Provides application ready for use. Everything is managed.
  Example:-
  - G-mail
  - Microsoft Office 365
  
- **Serverless or Function as a Service (Faas)**: We deploy only small, single purpose functions. Everything is abstracted. You pay for the compute resources used by the functions.
  Example:-
  - AWS Lambda
  - Azure functions
  - Google Cloud Functions

# Google Cloud Platform
## Google App Engine:
- PaaS - Deploy your code, don't worry about rest.
- Built in support for microservices, out-of-the box autoscaling.

## Goog;e Compute Engine:
- IaaS - Deploy and orchestrate clusters of VMs on Google architecture.
- can be managed by other tools like Ansible, Salt, Puppet and Chef.
  
## Google Cloud Functions:
- Google's Faas/Serverless Solution
- Quickley and easily create and deploy Faas functions

## Google Cloud SDK:
- SDK (software development kit) for interacting with GCP APIs.

## Stackdriver:
- GCP Monitoring solution.
- Monitoring, looging and diagonistics. Also works with AWS.

## Cloud Deployment Manager: (Configuration Management)
- Declarative configuration for GCp stack, TAML based.

## Google Kubernetes Engine:
- Orchestration on GCP with Kubernetes.
- Do continuous integration with Jenkins on Kubnetes Engine.

# Microsoft Aazure Platform
- Visual Studio Team Service :
- Jenkins :
- Continous Deployment Triggers :
- Azure Cintainer Registry : 
- Azure Container Service : Kubernetes orchestration
- Azure Web Apps : Cloud hosting
- Azure Application Insights : APM, diagonistics and Analytics. Support machine learning
- Azure Functions:

# Amazon Web Service Platform:
## Amazon EC2 (Elastic Compute Cloud):
- Iaas
- Easily scalable
- Full control over your cloud infrastructure.
- integrates with large number of tools both AWS and 3rd party.

## AWS Elastic Beanstalk
- Paas
- Out-of-the-box load balancing and autoscaling.
- Can still access underlying AWS resources with full control.

## AWS CodeBuild, AWS CodeDeploy, AWS CodePipeline & AWS CodeStar
- Continuous Integration, Delivery and Deployment
- AWS CodeBuild : Continous Integration.
- AWS CodeDeploy : Continuous deployment.
- AWS CodePipeline : full code pipeline from build to deploy.
- AWS CodeStar - Integrates all parts of process with project management tool and JIRA issue tracking.

## Infrastructure as code
- CloudForamtion : Stack templeting engine, YAML or JSON-based
- OpsWorks : IaC with Chef

## Serverless/FaaS
- AWS Lambda: run serverless functions on AWS.

## Monitoring
- Amazon Cloudwatch - track metrics and logs, set alarms, and automate responses to monitoring data.