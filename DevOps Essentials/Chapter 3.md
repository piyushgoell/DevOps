# DevOps Tools

Devops is NOT a set of tools.  
But, the DevOps communitry has created a wide range of powerful tools to meet those goals.  
The Part of doing DevOps is identifying the tools you need and learning how to use them.  
The Xebia Labs have created a neat way to explore some of the popular tools associated with DevOps.  
[The Periodic Table of Devops Tools](https://digital.ai/periodic-table-of-devops-tools)

## Tools for Build Automation & Continuous Integration

**Build Automation** - Automated processing of code in prepration for deployment.  
Example:- 
- Java - ant, maven, gradle
- JavaScript - npm, grunt, gulp
- Make - widely used in Unix-based system.
- Packer - build machine images and containers

**Continuous Integraation** - Continupusly merging code into single branch or mainline. It usually consist of server that integrated with the source control. When source code is changed, the server responds by executing a automated build.

 Example:-
 - Jenkins : OpenSource, Widely Used, Java Servlet based.
 - TravisCI : OpenSource, Build around Github integration, Executes build in clean VM.
 - Bamboo: Atlassian, out-of-the-box with othe atlassian products like JIRA and Confluence.

## Tools for Configuration Management
**Configuration Management** - Managing and changing the state of pieces of infrastructure in a consistent and maintainable way. They are great way to implement infrastructure as code.

Example:-
- Ansible : OpenSource, Declarative configuration, YAML configuration files, No control server needed, No agent needed. just python and ssh.
- Puppet : UI based, Declarative configuration, Uses Agent/server architecture, Puppet DSL
- Chef : Procedural configuration, Uses Agent/server, Chef DSL.
- Salt : Procedural configuration, Uses Agent/server, Uses YAML, Support for event-driven automation.

## Tools for Virtualization and Containerization
**Virtualization** - Managing resources by creating virtual rather than physical machines. It uses Hypervisor.

Example:-
- VMWare ESX and ESXi
- Microsoft Hyper-V
- Citrix XenServer

**Containers** - Lightweight, isolated packages containing everything needed to run a piece of software. It require fewer resources than VMs - VMs contains an entire OS plus virtual version of all the hardware. Containers have the bare minimum needed to run the software. Containers are still relatively new but very useful for DevOps.  
Example:-
- Docker : Currently the leading container technology

## Tools for Monitoring

**Monitoring** - Collecting and presenting data about the state and performance of applications.
1. *Infrastructure Monitoring* - focuses on things related to infrastructure.
   Example- CPU, RAM

2. *Application Performance Monitoring* - focuses on performance and stability of individual parts of an appliation.
   Example- Response times, logs

Example:-
Infrastructure Monitoring -
- SenSu : more sclable sollutions
- NewRelic : Saas  

Application Performance Monitoring - 
- AppDynamics - collects data prints about applications and presents it in a centralized dashboard.
- NewRelic : 
- Elastic Stack : quickly create views to aggregate data and easlity detect and diagnose problems.

## Tools for Orchestration
**Orchestration** - automation that supports processes and workflows, such as provisioning resources. It lets us scale up and scale down applications on request. Auto scale appliation based on usage.  
Example:- 
- Docker Swarm:
- Kubernetes: OpenSource, Manage containerized apps across multiple hosts.
- ZooKeeper: OpenSource - Apache foundation, work alongside Kubernetes.
- Terraform: combines orchestration and infrastructure-as-code. works well with Ansible, AWS and integrates with Kubernetes.