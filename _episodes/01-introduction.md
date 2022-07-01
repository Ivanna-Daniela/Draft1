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
Kubernetes provides you with a framework to run distributed systems resiliently. Kubernetes provides you with service discovery and load balancing, storage orchestration, automated rollouts and rollbacks, automatic bin packing, self-healing, secret and configuration management. 

## What is Kubernetes Cluster?
A Kubernetes cluster consists of "master" nodes and "worker" nodes. In short, master nodes share state to manage the cluster and schedule jobs to run on workers. It is considered best practice to run an odd number of masters.

## Kubernetes Components
When you deploy Kubernetes, you get a cluster. A Kubernetes cluster consists of a set of worker machines, called nodes. The worker nodes host the Pods that are the components of the application workload.

### Masters
Kubernetes masters share state via etcd, a distributed key-value store (KVS) implementing the Raft protocol. Do note that the state stored in etcd is scheduling state, service locations, and other cluster metadata; it does not keep state for the services running on the cluster.

### Workers
While master nodes are constantly sharing data, managing the control plane (routing inside the Kubernetes cluster), and scheduling services, workers primarily run pods.

## Nodes Components
| Component | Description |
| ----------- | ----------- |
| Pods | In the Kubernetes world, pods are the smallest computing unit. A pod is made up of one or more containers. While pods are essential for understanding Kubernetes, when writing services we don't actually deal in pods but one further abstraction, deployments, which create pods for us|
| Kubelet | The kubelet is the primary "node agent" that runs on each node.The kubelet takes a set of PodSpecs and ensures that the containers described in those PodSpecs are running and healthy. |
| Kube-Proxy| It reflects the services defined in the cluster and manages the rules to load-balance requests to a service’s backend pods.|

## Command line tool (kubectl)
Kubernetes provides a kubectl for communicating with a Kubernetes cluster's control plane, using the Kubernetes API.
Use the following syntax to run kubectl commands from your terminal window:
~~~
kubectl [command] [TYPE] [NAME] [flags]
~~~
where ```command ```, ```TYPE```, ```NAME```, and ```flags``` are:

```command:``` Specifies the operation that you want to perform on one or more resources, for example create, get, describe, delete.
```TYPE:``` Specifies the resource type.
```NAME:``` Specifies the name of the resource. 
 ```flags:```Specifies optional flags. 
 For installation instructions, see [Installing kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl); for a quick guide, see the [cheat sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/).
