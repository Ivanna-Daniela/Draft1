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
