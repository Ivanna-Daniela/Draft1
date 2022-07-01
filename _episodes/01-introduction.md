---
title: "Introduction"
teaching: 10
exercises: 15
questions:
- "What is Kubernetes?"
objectives:
- "Learn the very basics of Kubernetes"
keypoints:
- "First key point. Brief Answer to questions."
---
## What is Kubernetes?
Kubernetes is a container orchestration system open sourced by Google. Its main purpose is to schedule services to run on a cluster of computers while abstracting away the existence of the cluster from the services. Kubernetes is now maintained by the Cloud Native Computing Foundation, which is a part of the Linux Foundation. Kubernetes can flexibly handle replication, impose resource limits, and recover quickly from failures.

## Why you need Kubernetes?
Kubernetes provides you with a framework to run distributed systems resiliently. It takes care of scaling and failover for your application, provides deployment patterns, and more.

## What is Kubernetes Cluster?
A Kubernetes cluster consists of "master" nodes and "worker" nodes. In short, master nodes share state to manage the cluster and schedule jobs to run on workers. It is considered best practice to run an odd number of masters.

### Masters
Kubernetes masters share state via etcd, a distributed key-value store (KVS) implementing the Raft protocol. Do note that the state stored in etcd is scheduling state, service locations, and other cluster metadata; it does not keep state for the services running on the cluster.

### Workers
While master nodes are constantly sharing data, managing the control plane (routing inside the Kubernetes cluster), and scheduling services, workers primarily run pods.

### Pods
In the Kubernetes world, pods are the smallest computing unit. A pod is made up of one or more containers. While pods are essential for understanding Kubernetes, when writing services we don't actually deal in pods but one further abstraction, deployments, which create pods for us.


# Argo
Argo is a collection of open source tools that let us to extend the functions in Kubernetes.
We are going to explain 3 of the tools most important for working with argo.
###
![image](https://user-images.githubusercontent.com/70413460/176798180-3e3d6445-5b07-4087-94fd-174a998a6b03.png)
###
### 1. Argo workflow
Is used to execute complex job orchestration, including serial and parallel execution where each stage is executed like a container.

### 2. Argo Events
It is an integrator of workflows that use events from different sources like: webhook, S3, schedules, streams, etc.

### 3. Argo CD
It's a controller into kubernetes that supervises continually the applications in execute and compare their actually state.


# Autoscaling 
- Kubernetes supports autoscaling to optimise your nodes' resources as wll as adjust CPU and memory to meet your application's real usage. 
- If you need to save some money, you can scale down. Probably you want to pay for what you use, keep only with the resources when you need them

If you want to learn about pricing, ckeck the next link: https://cloud.google.com/compute/all-pricing
