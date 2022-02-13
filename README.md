# kubernetes



## Kubernetes' primary concepts
* `Clusters` : A cluster is a collection of hosts (nodes) 
* `Nodes` : A node is a single host. It may be a physical or virtual machine. Its job is to run pods.
* `The master` : The master is the control plane of Kubernetes. It consists of several components, such as an API server, a scheduler, and a controller manager. 
* `Pods` : A pod is the unit of work in Kubernetes. Each pod contains one or more containers.  All the containers in a pod have the same IP address and port space; they can communicate using localhost or standard inter-process communication.
* `Labels` : Labels are key-value pairs that are used to group together sets of objects – very often pods.  Note that labels are dedicated to identifying objects and not for attaching arbitrary metadata to objects. This is what annotations are for.
* `Annotations` : Annotations let you associate arbitrary metadata with Kubernetes objects.
* `Services` : Services are used to expose some functionality to users or other services.  They usually encompass a group of pods, usually identified by – you guessed it – a label.
* `Volume` : Container Storage Interface (CSI) 
* `Replication controllers and replica sets` :  
* `StatefulSet` : StatefulSet ensures (similar to a replication set) that a given number of instances with unique identities are running at any given time.
* `Secrets` : Secrets are small objects that contain sensitive info such as credentials and tokens. They are stored by default as plaintext in etcd, accessible by the Kubernetes API server, and can be mounted as files in pods (using dedicated secret volumes that piggyback on regular data volumes) that need access to them.
* `Names`
* `Namespaces` : A namespace is a kind of virtual cluster.



## The Kubernetes APIs
* DaemonSets
* Deployments
* HorizontalPodAutoscalers
* Ingress
* Jobs
* ReplicaSets

#### Resource categories
* `Workloads`: Objects you use to manage and run containers in the cluster
* `Discovery and Load Balancing`: Objects you use to expose your workloads to the world as externally accessible, load-balanced services
* `Config and Storage`: Objects you use to initialize and configure your applications, and to persist data that's outside the container
* `Cluster`: Objects that define how the cluster itself is configured; these are typically used only by cluster operators
* `Metadata`: Objects you use to configure the behavior of other resources within the cluster, such as HorizontalPodAutoscaler for scaling workloads

`<resource name>: <API group>`

##### The workloads API
* Container: core
* CronJob: batch
* DaemonSet: apps
* Deployment: apps
* Job: batch
* Pod: core
* ReplicaSet: apps
* ReplicationController: core
* StatefulSet: apps

##### Discovery and Load Balancing
* Endpoints: core
* Ingress: networking.k8s.io
* Service: core

#### Config and Storage
* ConfigMap: core
* CSIDriver: storage.k8s.io
* CSINode: storage.k8s.io
* Secret: core
* PersistentVolumeClaim: core
* StorageClass: storage.k8s.io
* Volume: storage.k8s.io
* VolumeAttachment: storage.k8s.io

#### Clusters
* Namespace: core
* Node: core
* PersistentVolume: core
* ResourceQuota: core
* Role: rbac.authorization.k8s.io
* RoleBinding: rbac.authorization.k8s.io
* ClusterRole: rbac.authorization.k8s.io
* ClusterRoleBinding: rbac.authorization.k8s.io
* NetworkPolicy: networking.k8s.io

##### Metadata


