# Kubernetes 101
==============
The following notes are from [this video](https://www.youtube.com/watch?v=H-FKBoWTVws)

before you go through these notes you should have  a basic knowledge of **Docker** & **Containers** & **Containerized applications**.

## What is Kubernetes & What does it solve?

Kubernetes is an open source system for _automatig deployment_, _scaling_, and _management_ of containerized applications.

If you want to have an application with _24/7 up-time_, _to have the avability to deploy updates to your code multiple times a day_, _to use cloud resources efficiently via container orchestration_, _to have a fault-tolerent & self healing system_ , _to be able to scale it like `hooloo`_, Kubernetes is for you.

## Kubernetes Architecture 

Basically in Kubernetes you're pooling resources.

> Kubernetes is like a big bucket that you can throw a whole bunch of Legos in and if they fit, they fit! Legos are containers & the bucket is the whole cluster, the bucket size is basically the some of CPU & RAM & other hardware/virtual resources in the kubernetes cluster. Kubertnetes handles the resources used by the containers inside it, e.g. if a container doesn't need much CPU kubernetes manages to supply it with just the amount of cpu it needs and give keep the rest of the CPU available for other containers