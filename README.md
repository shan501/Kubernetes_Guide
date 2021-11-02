# Kubernetes Guide
Created this guide after watching this YouTube video. https://www.youtube.com/watch?v=s_o8dwzRlu4&t=2467s
## Introduction
Kubernetes is a containers orchestration tool developed by Google.It helps you managed thousands of containers in many
different deployment enviorment(Virtual Machines , Cloud ,Hyprid).Since applications are moving away from monolithic 
archetectture , containers have been more and more popular.As a result , applications can have thousands of containers 
and managing them can be really hard.This is where Kubernetes comes in.Kubernetes offeres high availability , scalibility , 
and resilience.

## Kubernetes Architecture
A cluster is a bunch of Kubernetes nodes working together.Each cluster must have one Master node.The master node sends
instructions to other nodes called workers to perform certain tasks.Each node have something called Kubelet.This is what allows
them to communicate with each other.

