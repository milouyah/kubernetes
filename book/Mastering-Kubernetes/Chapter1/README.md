# Chapter 1: Understanding Kubernetes Architecture 
## 1.1 What is Kubernetes? 
### What Kubernetes is not 2
### Understanding container orchestration 3
#### Physical machines, virtual machines, and containers 3
#### The benefits of containers 3
#### Containers in the cloud 4
#### Cattle versus pets 5

## 1.2 Kubernetes concepts 5
### Clusters 6
### Nodes 6
### The master 7
### Pods 7
### Labels 8
### Annotations 8
### Label selectors 9
### Services 9
### Volume 10
### Replication controllers and replica sets 10
### StatefulSet 10
### Secrets 11
### Names 11
### Namespaces 11

## 1.3 Diving into Kubernetes architecture in depth 12
### 1.3.1 Distributed system design patterns 12
#### The sidecar pattern 13
#### The ambassador pattern 13
#### The adapter pattern 13
#### Multi-node patterns 14

### 1.3.2 The Kubernetes APIs 14
#### Resource categories 15

### 1.3.3 Kubernetes components 18
#### 1.3.3.1 KMaster components 18
The master components `can all run on one node`, but in a highly available setup or a very large cluster, they may be `spread across multiple nodes`.

* The API server
* Etcd - Etcd is a highly reliable `distributed data store`.
* The Kube controller manager - The Kube controller manager is a collection of various managers rolled up into one binary.
* Cloud controller managers
* `kube-scheduler` - Kube-scheduler is responsible for scheduling pods into nodes. It oversees communicating with the master components and manages the running pods.
* DNS
#### 1.3.3.2 Node components 21
* Proxy
* Kubelet - The kubelet is the Kubernetes representative on the node.

## 1.4 Kubernetes runtimes 22
### The container runtime interface (CRI) 23
### Docker 25
### rkt 27
#### App container 27
### CRI-O 27
### Hyper containers 28
#### Frakti 28
#### Stackube 28

## 1.5 Continuous integration and deployment 28
### What is a CI/CD pipeline? 29
### Designing a CI/CD pipeline for Kubernetes 30