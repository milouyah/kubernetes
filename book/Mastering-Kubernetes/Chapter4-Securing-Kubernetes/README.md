# Chapter 4: Securing Kubernetes 95
## 4.1 Understanding Kubernetes security challenges 96
### Node challenges 96
### Network challenges 97
### Image challenges 99
### Configuration and deployment challenges 100
### Pod and container challenges 101
### Organizational, cultural, and process challenges 102

## 4.2 Hardening Kubernetes 103
### Understanding service accounts in Kubernetes 103
* How does Kubernetes manage service accounts? 105

## 4.3 Accessing the API server 105
### Authenticating users 106
### Authorizing requests 108
### Using admission control plugins 110

## 4.4 Securing pods 112
### Using a private image repository 112
### ImagePullSecrets 112
### Specifying a security context 113
### Protecting your cluster with AppArmor 114
### Pod security policies 116
### Authorizing pod security policies via RBAC 117

## 4.5 Managing network policies 118
### Choosing a supported networking solution 119
### Defining a network policy 119
### Limiting egress to external networks 121
### Cross-namespace policies 122

## 4.6 Using secrets 122
### Storing secrets in Kubernetes 122
### Configuring encryption at rest 122
### Creating secrets 123
### Decoding secrets 124
### Using secrets in a container 124

## 4.7 Running a multi-user cluster 125
### The case for a multi-user cluster 126
### Using namespaces for safe multi-tenancy 126
### Avoiding namespace pitfalls 127
