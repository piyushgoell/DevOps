## What is Container ?

A container is a standard unit of software that packages up code and all of its dependencies so that application runs quickly and reliably from one computing environment to another.

Advantages:

1. Portability : Containers let you run software easily in a variety of envirnoments.
2. Consistency : Conatiners helps software run in the same way no matter which environment you are running in.
3. Low Overhead : Container use fewer resources than some other technologies, such as virtual machines.

Container Runtimes : It is the software used to run container on a machine. 
There are many runtime available like containerd www.containerd.io

## What is Kubernetes?

It is an open-source system for automating deployment, scaling and management of containerized applications.

1. It helps you deploy containers across a pool of compute resources, such as servers.
2. It helps ypu manage multiple replicas of your application to multiple servers.
3. It makes it easy to scale up and scale down
4. Networking : It manages and controlls container network communications
5. Security: It provides ability to build more secure applications.
6. Configuration Management : It helps in managing application configurations and pass configuration data to your container.

## Kubernetes Clusters

A Kubernetes Cluster is a collection of worker machines that run containers.

The control plane controls the cluster and it serves as an interface for us to interact with the cluster. So, control plane controls the cluster and worker nodes are responsible for actually running the containers. 
So, Woker nodes is a machine that runs containers within the cluster and each node is only responsible for running and managing the containers that are actually located on that particluar node. The Worker node also monitors the state of the containers that are running on that node and it also reports the state information back to the control plane. Each Worker nodes have a container runtime to manage containers.

## Building a Kubernetes Cluster

### What is kuberadm?
It is an open source container orchestration tool for containers.
It is a tool that will simplyfy the process of setting up our kubernetes cluster.


## What is Kubernetes API?

"The core of Kubernetes control plane is the API server"
1. It is a basic HTTP API.
2. It is the primary user interface that lets users query and manipulate objects, thereby controlling the cluster.
3. It is the centeral point of communication with each other for Kubernetes Cluster.

## kubernetes Object
They are persistent data entities stored by kubernetes. They represent the state of the cluster.

## Kubernetes Pods
There are different types of kubernetes Objects. The Pods are most important and used to run and manage containers.

## Kubectl basics

kubectl lets you interact with kubernetes from command line.  
It works primarity by allowing user to view, create, modify and delete Kubernetes Objects.  
Kubectl communicates with the Kubernetes API behind the scenes to carry out the user commands.  

        vim my-service.yml
        kubectl create -f my-service.yml --save-config
        kubectl get service
        kubectl get service my-service
        kubectl describe service my-service
        kubectl apply -f  my-service.yml
        kubectl delte service my-service

## Managing Container with Pods

        apiVersion: v1
        kind: Pod [Specifies the object type as Pod]
        metadata:
            name: web-frontend [the name of the Pod Object]
        spec:
            containers: [Specifies the list of one or more containers included in the Pod]
            - name: nginx
                image: nginx [Specifies the name of the container image containing the software you want to run]
            - ports:
               - containerPort: 80 [Specifies the Port is exposed on port 80]

## Kubernetes in the Cloud

### Kubernetes on AWS

Amazon EKS (Amazon Elastic Kubernetes Service) : allows to easily run applications on a managed Kubernetes infrastrucutre.

Amazon EC2 (Amazon Elastic Compute Cloud) : allows to build and manage kubernetes cluster by yourself

Amazon ECR (Amazon Elastic Container Registry) : provides a place to securely store and manage container images in the cloud.

### Kubernetes on Azure

Azure Kubernetes Service (AKS) : provides a managed kubernetes platform within Microsoft Azure.
It integrates with Azure  CI/CD pipelines

### Kubernetes on Google

Google Kubernetes Engine (GKE) : It includes feature for high availability, such as multi-zone and regional clusters.