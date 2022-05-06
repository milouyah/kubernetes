
# [Mastering Kubernetes](https://subscription.packtpub.com/product/programming/9781839211256)


# Chapter 1: Understanding Kubernetes Architecture 
## What is Kubernetes? 
### What Kubernetes is not 2
### Understanding container orchestration 3
#### Physical machines, virtual machines, and containers 3
#### The benefits of containers 3
#### Containers in the cloud 4
#### Cattle versus pets 5

## Kubernetes concepts 5
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

## Diving into Kubernetes architecture in depth 12
### Distributed system design patterns 12
#### The sidecar pattern 13
#### The ambassador pattern 13
#### The adapter pattern 13
#### Multi-node patterns 14

### The Kubernetes APIs 14
#### Resource categories 15

### Kubernetes components 18
#### Master components 18
#### Node components 21

## Kubernetes runtimes 22
### The container runtime interface (CRI) 23
### Docker 25
### rkt 27
#### App container 27
### CRI-O 27
### Hyper containers 28
#### Frakti 28
#### Stackube 28

## Continuous integration and deployment 28
### What is a CI/CD pipeline? 29
### Designing a CI/CD pipeline for Kubernetes 30

----

# Chapter 2: Creating Kubernetes Clusters 31
Overview 31
Creating a single-node cluster with Minikube 32
Meet kubectl 32
Quick introduction to Minikube 33
Getting ready 33
On Windows 33
On macOS 34
Creating the cluster 35
Troubleshooting 36
Checking out the cluster 37
Doing work 38
Examining the cluster with the dashboard 40
Creating a multi-node cluster with KinD 42
Quick introduction to KinD 42
Installing KinD 42
Creating the cluster with KinD 43
Doing work with KinD 46
Accessing Kubernetes services locally though a proxy 46
Creating a multi-node cluster with k3d 47
Quick introduction to k3s and k3d 48
Table of Contents
[ iii ]
Installing k3d 48
Creating the cluster with k3d 49
Comparing Minikube, KinD, and k3d 51
Creating clusters in the cloud (GCP, AWS, Azure) 52
The cloud-provider interface 52
GCP 53
AWS 53
Kubernetes on EC2 54
AWS EKS 55
Fargate 55
Azure 56
Other cloud providers 56
Once upon a time in China 57
IBM Kubernetes Service 57
Oracle Container Service 58
Creating a bare-metal cluster from scratch 58
Use cases for bare metal 58
When should you consider creating a bare-metal cluster? 59
Understanding the process 59
Using virtual private cloud infrastructure 60
Building your own cluster with Kubespray 60
Building your cluster with KRIB 60
Building your cluster with RKE 61
Bootkube 61
References 62

----

# Chapter 3: High Availability and Reliability 63
## High availability concepts 64
Redundancy 64
Hot swapping 64
Leader election 65
Smart load balancing 65
Idempotency 66
Self-healing 66
High availability best practices 66
Creating highly available clusters 67
Making your nodes reliable 68
Protecting your cluster state 69
Clustering etcd 69
Verifying the etcd cluster 73
Protecting your data 73
Running redundant API servers 74
Table of Contents
[ iv ]
Running leader election with Kubernetes 74
Making your staging environment highly available 75
Testing high availability 76
High availability, scalability, and capacity planning 77
Installing the cluster autoscaler 78
Considering the vertical pod autoscaler 80
Live cluster updates 80
Rolling updates 81
Complex deployments 83
Blue-green deployments 84
Canary deployments 85
Managing data-contract changes 86
Migrating data 86
Deprecating APIs 87
Large cluster performance, cost, and design trade-offs 88
Availability requirements 88
Best effort 88
Maintenance windows 89
Quick recovery 90
Zero downtime 90
Site reliability engineering 92
Performance and data consistency 93
Summary 93
References 94
Chapter 4: Securing Kubernetes 95
Understanding Kubernetes security challenges 96
Node challenges 96
Network challenges 97
Image challenges 99
Configuration and deployment challenges 100
Pod and container challenges 101
Organizational, cultural, and process challenges 102
Hardening Kubernetes 103
Understanding service accounts in Kubernetes 103
How does Kubernetes manage service accounts? 105
Accessing the API server 105
Authenticating users 106
Authorizing requests 108
Using admission control plugins 110
Securing pods 112
Using a private image repository 112
ImagePullSecrets 112
Table of Contents
[ v ]
Specifying a security context 113
Protecting your cluster with AppArmor 114
Pod security policies 116
Authorizing pod security policies via RBAC 117
Managing network policies 118
Choosing a supported networking solution 119
Defining a network policy 119
Limiting egress to external networks 121
Cross-namespace policies 122
Using secrets 122
Storing secrets in Kubernetes 122
Configuring encryption at rest 122
Creating secrets 123
Decoding secrets 124
Using secrets in a container 124
Running a multi-user cluster 125
The case for a multi-user cluster 126
Using namespaces for safe multi-tenancy 126
Avoiding namespace pitfalls 127
Summary 128
References 128
Chapter 5: Using Kubernetes Resources in Practice 129
Designing the Hue platform 129
Defining the scope of Hue 130
Smart reminders and notifications 130
Security, identity, and privacy 130
Hue components 131
Hue microservices 133
Planning workflows 135
Automatic workflows 135
Human workflows 135
Budget-aware workflows 135
Using Kubernetes to build the Hue platform 136
Using kubectl effectively 136
Understanding kubectl resource configuration files 137
ApiVersion 138
Kind 138
Metadata 138
Spec 138
Deploying long-running microservices in pods 139
Creating pods 139
Decorating pods with labels 141
Deploying long-running processes with deployments 142
Updating a deployment 143
Separating internal and external services 144
Table of Contents
[ vi ]
Deploying an internal service 145
Creating the Hue-reminders service 146
Exposing a service externally 148
Ingress 149
Advanced scheduling 150
Node selector 150
Taints and tolerations 151
Node affinity and anti-affinity 153
Pod affinity and anti-affinity 153
Using namespaces to limit access 154
Using kustomization for hierarchical cluster structures 156
Understanding the basics of kustomize 156
Configuring the directory structure 157
Applying kustomizations 158
Patching 160
Kustomizing the entire staging namespace 160
Launching jobs 162
Running jobs in parallel 163
Cleaning up completed jobs 164
Scheduling cron jobs 164
Mixing non-cluster components 166
Outside-the-cluster-network components 166
Inside-the-cluster-network components 167
Managing the Hue platform with Kubernetes 167
Using liveness probes to ensure your containers are alive 167
Using readiness probes to manage dependencies 168
Employing init containers for orderly pod bring-up 169
Pod readiness and readiness gates 170
Sharing with DaemonSet pods 171
Evolving the Hue platform with Kubernetes 172
Utilizing Hue in an enterprise 172
Advancing science with Hue 173
Educating the kids of the future with Hue 173
Summary 173
References 174
Chapter 6: Managing Storage 175
Persistent volumes walkthrough 175
Volumes 176
Using emptyDir for intra-pod communication 176
Using HostPath for intra-node communication 178
Using local volumes for durable node storage 180
Provisioning persistent volumes 181
Table of Contents
[ vii ]
Provisioning persistent volumes externally 182
Creating persistent volumes 182
Capacity 183
Volume mode 183
Access modes 183
Reclaim policy 184
Storage class 184
Volume type 185
Mount options 185
Making persistent volume claims 185
Mounting claims as volumes 188
Raw block volumes 189
Storage classes 191
Default storage class 192
Demonstrating persistent volume storage end to end 192
Public cloud storage volume types – GCE, AWS, and Azure 198
Amazon EBS 198
Amazon EFS 199
GCE persistent disk 201
Azure data disk 202
Azure Files 203
GlusterFS and Ceph volumes in Kubernetes 204
Using GlusterFS 205
Creating endpoints 205
Adding a GlusterFS Kubernetes service 206
Creating pods 207
Using Ceph 208
Connecting to Ceph using RBD 208
Connecting to Ceph using CephFS 210
Flocker as a clustered container data volume manager 211
Integrating enterprise storage into Kubernetes 212
Rook – the new kid on the block 213
Projecting volumes 214
Using out-of-tree volume plugins with FlexVolume 215
The Container Storage Interface 216
Volume snapshotting and cloning 217
Volume snapshots 217
Volume cloning 218
Summary 219
Chapter 7: Running Stateful Applications with Kubernetes 221
Stateful versus stateless applications in Kubernetes 221
Understanding the nature of distributed data-intensive apps 222
Why manage state in Kubernetes? 222
Why manage state outside of Kubernetes? 222
Table of Contents
[ viii ]
Shared environment variables versus DNS records for discovery 223
Accessing external data stores via DNS 223
Accessing external data stores via environment variables 223
Consuming a ConfigMap as an environment variable 224
Using a redundant in-memory state 225
Using DaemonSet for redundant persistent storage 226
Applying persistent volume claims 226
Utilizing StatefulSets 226
Running a Cassandra cluster in Kubernetes 228
Quick introduction to Cassandra 229
The Cassandra Docker image 230
Hooking up Kubernetes and Cassandra 238
Creating a Cassandra headless service 241
Using StatefulSets to create the Cassandra cluster 241
Summary 246
Chapter 8: Deploying and Updating Applications 247
Horizontal pod autoscaling 248
Declaring an HPA 248
Custom metrics 251
Autoscaling with Kubectl 251
Performing rolling updates with autoscaling 254
Handling scarce resources with limits and quotas 257
Enabling resource quotas 258
Resource quota types 258
Compute resource quota 258
Storage resource quota 259
Object count quota 260
Quota scopes 261
Resource quotas and priority classes 261
Requests and limits 262
Working with quotas 262
Using namespace-specific context 262
Creating quotas 262
Using limit ranges for default compute quotas 267
Choosing and managing the cluster capacity 268
Choosing your node types 268
Choosing your storage solutions 269
Trading off cost and response time 269
Using multiple node configurations effectively 270
Benefiting from elastic cloud resources 270
Autoscaling instances 270
Mind your cloud quotas 271
Manage regions carefully 271
Considering container-native solutions 272
Table of Contents
[ ix ]
Pushing the envelope with Kubernetes 273
Improving the performance and scalability of Kubernetes 274
Caching reads in the API server 274
The pod lifecycle event generator 274
Serializing API objects with protocol buffers 276
etcd3 276
Other optimizations 277
Measuring the performance and scalability of Kubernetes 277
The Kubernetes SLOs 277
Measuring API responsiveness 277
Measuring end-to-end pod startup time 279
Testing Kubernetes at scale 280
Introducing the Kubemark tool 281
Setting up a Kubemark cluster 281
Comparing a Kubemark cluster to a real-world cluster 281
Summary 282
Chapter 9: Packaging Applications 283
Understanding Helm 283
The motivation for Helm 284
The Helm 2 architecture 284
Helm 2 components 284
The Tiller server 284
The Helm client 285
Helm 3 285
Using Helm 285
Installing Helm 286
Installing the Helm client 286
Installing the Tiller server for Helm 2 286
Finding charts 287
Adding repositories 288
Installing packages 290
Checking the installation status 292
Customizing a chart 296
Additional installation options 298
Upgrading and rolling back a release 298
Deleting a release 299
Working with repositories 300
Managing charts with Helm 301
Taking advantage of starter packs 302
Creating your own charts 302
The Chart.yaml file 303
Versioning charts 303
The appVersion field 303
Deprecating charts 304
Chart metadata files 304
Table of Contents
[ x ]
Managing chart dependencies 304
Managing dependencies with requirements.yaml 305
Utilizing special fields in requirements.yaml 306
Using templates and values 307
Writing template files 307
Testing and troubleshooting your charts 309
Embedding built-in objects 311
Feeding values from a file 312
Scope, dependencies, and values 313
Summary 315
Chapter 10: Exploring Advanced Networking 317
Understanding the Kubernetes networking model 318
Intra-pod communication (container to container) 318
Inter-pod communication (pod to pod) 318
Pod-to-service communication 319
External access 319
Kubernetes networking versus Docker networking 320
Lookup and discovery 322
Self-registration 322
Services and endpoints 322
Loosely coupled connectivity with queues 323
Loosely coupled connectivity with data stores 323
Kubernetes ingress 324
Kubernetes network plugins 324
Basic Linux networking 324
IP addresses and ports 324
Network namespaces 325
Subnets, netmasks, and CIDRs 325
Virtual Ethernet devices 325
Bridges 325
Routing 325
Maximum transmission unit 326
Pod networking 326
Kubenet 326
Container networking interface 327
Kubernetes networking solutions 332
Bridging on bare metal clusters 332
Contiv 332
Open vSwitch 333
Nuage networks VCS 335
Flannel 335
Calico 337
Romana 337
Weave Net 340
Using network policies effectively 340
Table of Contents
[ xi ]
Understanding the Kubernetes network policy design 340
Network policies and CNI plugins 341
Configuring network policies 341
Implementing network policies 342
Load balancing options 342
External load balancer 343
Configuring an external load balancer 344
Finding the load balancer IP addresses 344
Preserving client IP addresses 345
Understanding even external load balancing 346
Service load balancing 346
Ingress 347
HAProxy 349
MetalLB 351
Keepalived VIP 351
Traefic 351
Writing your own CNI plugin 352
First look at the loopback plugin 352
Building on the CNI plugin skeleton 356
Reviewing the bridge plugin 359
Summary 362
Chapter 11: Running Kubernetes on Multiple Clouds
and Cluster Federation 365
The history of cluster federation on Kubernetes 366
Understanding cluster federation 366
Important use cases for cluster federation 368
Capacity overflow 368
Sensitive workloads 368
Avoiding vendor lock-in 369
Geo-distributing high availability 369
Learning the basics of Kubernetes federation 370
Defining basic concepts 370
Federation building blocks 370
Federation features 372
The KubeFed control plane 372
The federation API server 372
The federation controller manager 372
The hard parts 373
Federated unit of work 374
Location affinity 374
Cross-cluster scheduling 375
Federated data access 376
Federated auto-scaling 376
Managing a Kubernetes Cluster Federation 377
Installing kubefedctl 377
Table of Contents
[ xii ]
Creating clusters 379
Configuring the Host Cluster 379
Registering clusters with the federation 381
Working with federated API types 381
Federating resources 382
Federating an entire namespace 384
Checking the status of federated resources 384
Using overrides 385
Using placement to control federation 385
Debugging propagation failures 387
Employing higher-order behavior 387
Utilizing multi-cluster Ingress DNS 387
Utilizing multi-cluster Service DNS 388
Utilizing multi-cluster scheduling 389
Introducing the Gardener project 392
Understanding the terminology of Gardener 392
Understanding the conceptual model of Gardener 393
Diving into the Gardener architecture 394
Managing cluster state 394
Managing the control plane 395
Preparing the infrastructure 395
Using the Machine controller manager 395
Networking across clusters 395
Monitoring clusters 395
The gardenctl CLI 396
Extending Gardener 397
Gardener ring 401
Summary 402
Chapter 12: Serverless Computing on Kubernetes 405
Understanding serverless computing 405
Running long-running services on "serverless" infrastructure 406
Running FaaS on "serverless" infrastructure 407
Serverless Kubernetes in the cloud 408
Don't forget the cluster autoscaler 408
Azure AKS and Azure Container Instances 409
AWS EKS and Fargate 410
Google Cloud Run 412
Knative 413
Knative Serving 413
The Knative Service object 414
The Knative Route object 416
The Knative Configuration object 417
The Knative Revision object 420
Table of Contents
[ xiii ]
Knative Eventing 420
Getting familiar with Knative Eventing terminology 420
The architecture of Knative Eventing 422
Taking Knative for a ride 423
Installing Knative 424
Deploying a Knative service 426
Invoking a Knative service 426
Checking the scale-to-zero option in Knative 427
Kubernetes FaaS frameworks 428
Fission 429
Fission Workflows 430
Experimenting with Fission 432
Kubeless 434
Kubeless architecture 434
Playing with Kubeless 435
Using the Kubeless UI 437
Kubeless with the serverless framework 438
Knative and riff 439
Understanding riff runtimes 439
Installing riff with Helm 2 439
Summary 442
Chapter 13: Monitoring Kubernetes Clusters 443
Understanding observability 444
Logging 444
Log format 445
Log storage 445
Log aggregation 445
Metrics 445
Distributed tracing 446
Application error reporting 447
Dashboards and visualization 447
Alerting 448
Logging with Kubernetes 448
Container logs 448
Kubernetes component logs 449
Centralized logging 450
Choosing a log collection strategy 450
Cluster-level central logging 452
Remote central logging 452
Dealing with sensitive log information 453
Using Fluentd for log collection 453
Collecting metrics with Kubernetes 454
Monitoring with the metrics server 455
Exploring your cluster with the Kubernetes dashboard 457
Table of Contents
[ xiv ]
The rise of Prometheus 458
Installing Prometheus 460
Interacting with Prometheus 462
Incorporating kube-state-metrics 462
Utilizing the node exporter 464
Incorporating custom metrics 466
Alerting with Alertmanager 466
Visualizing your metrics with Grafana 468
Considering Loki 470
Distributed tracing with Jaeger 470
What is OpenTracing? 471
OpenTracing concepts 472
Introducing Jaeger 472
Jaeger architecture 473
Installing Jaeger 475
Troubleshooting problems 478
Taking advantage of staging environments 478
Detecting problems at the node level 479
Problem daemons 479
Dashboards versus alerts 480
Logs versus metrics versus error reports 481
Detecting performance and root cause with distributed tracing 482
Summary 482
Chapter 14: Utilizing Service Meshes 483
What is a service mesh? 483
Control plane and data plane 487
Choosing a service mesh 487
Envoy 487
Linkerd 2 487
Kuma 488
AWS App Mesh 488
Maesh 488
Istio 488
Incorporating Istio into your Kubernetes cluster 489
Understanding the Istio architecture 489
Envoy 490
Pilot 490
Mixer 491
Citadel 491
Galley 492
Preparing a minikube cluster for Istio 492
Installing Istio 493
Installing Bookinfo 495
Table of Contents
[ xv ]
Traffic management 499
Security 502
Istio identity 503
Istio PKI 504
Istio authentication 504
Istio authorization 505
Policies 509
Monitoring and observability 512
Logs 513
Metrics 516
Distributed tracing 519
Visualizing your service mesh with Kiali 522
Summary 523
Chapter 15: Extending Kubernetes 525
Working with the Kubernetes API 525
Understanding OpenAPI 526
Setting up a proxy 526
Exploring the Kubernetes API directly 526
Using Postman to explore the Kubernetes API 528
Filtering the output with HTTPie and jq 529
Creating a pod via the Kubernetes API 530
Accessing the Kubernetes API via the Python client 531
Dissecting the CoreV1API group 532
Listing objects 534
Creating objects 534
Watching objects 535
Invoking Kubectl programmatically 536
Using Python subprocesses to run Kubectl 536
Extending the Kubernetes API 538
Understanding Kubernetes extension points and patterns 539
Extending Kubernetes with plugins 539
Extending Kubernetes with the cloud controller manager 540
Extending Kubernetes with webhooks 541
Extending Kubernetes with controllers and operators 541
Extending Kubernetes scheduling 542
Extending Kubernetes with custom container runtimes 542
Introducing custom resources 542
Developing custom resource definitions 543
Integrating custom resources 545
Dealing with unknown fields 546
Finalizing custom resources 548
Adding custom printer columns 548
Understanding API server aggregation 549
Utilizing the service catalog 550
Writing Kubernetes plugins 552
Table of Contents
[ xvi ]
Writing a custom scheduler 552
Understanding the design of the Kubernetes scheduler 552
Scheduling pods manually 555
Preparing our own scheduler 556
Assigning pods to the custom scheduler 557
Verifying that the pods were scheduled using the correct scheduler 558
Writing Kubectl plugins 559
Understanding Kubectl plugins 559
Managing Kubectl plugins with Krew 560
Creating your own Kubectl plugin 561
Kubectl plugin gotchas 562
Don't forget your shebangs! 562
Naming 562
Overriding existing Kubectl commands 562
Flat namespace for Krew plugins 563
Employing access control webhooks 563
Using an authentication webhook 564
Using an authorization webhook 566
Using an admission control webhook 568
Configuring a webhook admission controller on the fly 568
Providing custom metrics for horizontal pod autoscaling 570
Extending Kubernetes with custom storage 571
Summary 572
Chapter 16: The Future of Kubernetes 575
The Kubernetes momentum 576
The importance of the CNCF 576
Project curation 576
Certification 577
Training 578
Community and education 578
Tooling 578
The rise of managed Kubernetes platforms 579
Public cloud Kubernetes platforms 579
Bare-metal, private clouds, and Kubernetes on the edge 579
Kubernetes Platform as a Service (PaaS) 580
Upcoming trends 580
Security 580
Networking 581
Custom hardware and devices 582
Service mesh 582
Serverless computing 583
Kubernetes on the Edge 583
Native CI/CD 584
Operators 584
Table of Contents
[ xvii ]
Summary 585
References 585
Other Books You May Enjoy 587
Index 591