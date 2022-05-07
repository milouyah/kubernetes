# Chapter 3: High Availability and Reliability 63

## 3.1 High availability concepts 64
### 1. Redundancy 64
### 2. Hot swapping 64
* Give up on in-flight transactions
* Keep a hot replica in sync
### 3. Leader election 65
### 4. Smart load balancing 65
### 5. [Idempotency](https://en.wikipedia.org/wiki/Idempotence)
Thus, most
systems opt to support at-least-once semantics, which means it is OK for the same work to be performed multiple times without violating the system's data integrity.
### 6. Self-healing 66

## 3.2 High availability best practices 66

* [kubespray](https://kubespray.io/#/)
* Heapster

### 3.2.1. Creating highly available clusters 
* To create a highly available Kubernetes cluster, the master components must be redundant.
* That means etcd must be deployed as a cluster (typically across three
or five nodes) and the Kubernetes API server must be redundant.



### 3.2.2. Making your nodes reliable 68
### 3.2.3. Protecting your cluster state 
`etcd operator`
```
• Create and destroy
• Resizing
• Failovers
• Rolling upgrades
• Backup and restore
```

#### 3.2.3.1 Clustering etcd 
* You should have at least `three nodes` in your etcd cluster.
* If you need more reliability and redundancy, you can go for `five, seven, or any other odd number of nodes`.

1. Installing the etcd operator
```bash
k apply -f helm-rbac.yaml
helm2 init --service-account tiller
helm2 install stable/etcd-operator --name x
```

2. Crateing the etcd Cluster
```
k create -f etcd-cluster.yaml
k get pods -o wide | grep etcd-cluster
```


#### 3.2.3.2 Verifying the etcd cluster 
```
k exec etcd-cluster-2fs2lpz7p7 -- etcdctl cluster-health
k exec etcd-cluster-2fs2lpz7p7 -- etcdctl set test "Yeah, it works"
k exec etcd-cluster-2fs2lpz7p7 -- etcdctl get test
```

### 4. Protecting your data 
* [Velero](https://velero.io)
  
### 5. Running redundant API servers 74
### 6. Running leader election with Kubernetes 74
### 7. Making your staging environment highly available 75
### 8. Testing high availability 76

## 3.3 High availability, scalability, and capacity planning 
* horizontal pod autoscaler (HPA)
* cluster autoscaler (CA)
### Installing the `cluster autoscaler` 
### Considering the `vertical pod autoscaler` 

## 3.5 Live cluster updates 80
### Rolling updates 81
* Complex deployments 83
### Blue-green deployments 84
### Canary deployments 85
### Managing data-contract changes 86
### Migrating data 86
### Deprecating APIs 87

## 3.5 Large cluster performance, cost, and design trade-offs 88
### Availability requirements 88
### Best effort 88
### Maintenance windows 89
### Quick recovery 90
### Zero downtime 90
### Site reliability engineering (SRE)
SRE embraces failures and works with `service-level indicators (SLIs)`, `service-level objectives (SLOs)`, and `service-level agreements (SLAs)`. Each

### Performance and data consistency 
* CAP stands for consistency, availability, and partition tolerance.


<br><br>

# See

* [kubespray](https://kubespray.io/#/)
* Heapster
* [Velero](https://velero.io)