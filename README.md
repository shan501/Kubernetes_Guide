# Kubernetes Guide
Created this guide after watching this YouTube video. https://www.youtube.com/watch?v=s_o8dwzRlu4&t=2467s

## Introduction
Kubernetes is a containers orchestration tool developed by Google.It helps you managed thousands of containers in many
different deployment enviorment(Virtual Machines , Cloud ,Hyprid).Since applications are moving away from monolithic 
archetectture , containers have been more and more popular.As a result , applications can have thousands of containers 
and managing them can be really hard.This is where Kubernetes comes in.Kubernetes offeres high availability , scalibility , 
and resilience.

## Kubernetes Architecture
A cluster is a bunch of Kubernetes nodes working together.Each cluster must have at least one Master node.The master node sends
instructions to other nodes called workers to perform certain tasks.Each node have something called Kubelet.This is what is used
to send instructions to worker nodes.Work nodes contains the containers that are running.The master nodes also contains a container.
There is a API server within that container , and that is what allows us to talk to kubernetes either through a UI,API,or CLI.
There is also a contoller manager container which keeps tracks of what is happenning in the cluster.It also contains a
Sceduler container which decides the placement of pods.Finally there is a etcd container which contains the data of the current state
of the cluster.You can create snapshots from the etcd container for backups.A virtual network allows the nodes to talk to each other.
For high availibility there is typically more than one master node in a cluster

## Kubernetes Components 

### Nodes and Pods
A node contains a bunch of working pods.
Pod is a abstraction of a container.It will have applications running on it just like a container.You can have more than one applications
on it but typically it is just one.Each pod gets its on ip address , the containers in the pod does not.However , the ip address is ephemeral.

### Service
Since the ip address is ephemeral , it would be unconvinient if a container crash and we have to change the ip address if we are communicating
using it.We would have to update the ip address each time.We can use Service.Service is a permanent ip address to each pod.There are external 
and internal services.The external services can be accessed by users and internal service can not.A ingress is used to map a domain name 
to your services and forward the traffic. 

### ConfigMap and Secrets
When you want to change some configuration of your pod , you might have to rebuild the image,push it to a repo , and pull it and run it again.This
be really tedious.Similar to enviormental variables in Docker.You can use ConfigMap in Kubernets.You would connect a config map to a container.
And if you want to make configuration changes to it , you would just make the changes to configmap.It should not contain sensitive data.If you 
want to store sensitive data , there is something called secret.For example a user might change their password, so you would want to change it on 
your container.You can use secrets to do that.It is encoded in base-64 but there are third-party tools that can help you encrypt it.

### Volume
The data generated on the pods are ephermeral so if you want to store the data permantly you can use volumes.


