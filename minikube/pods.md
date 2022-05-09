# Pods

## List Pods using Kubectl
* Info: Add `-o` wide option to the kubectl get command to get more details.  
  
List Pods in the default Namespace for the current context:
```
$ kubectl get pods
$ kubectl get pods -o wide
```

List all Pods from all Namespaces:
```
$ kubectl get pods --all-namespaces 
$ kubectl get pods --all-namespaces -o wide
```
Get Pods from a particular Namespace:
```
$ kubectl get pods --namespace <namespace_name>
$ kubectl get pods --namespace <namespace_name> -o wide
```

Get Pods running on a specific Node:
```
$ kubectl get pods --field-selector spec.nodeName=<node_name>
$ kubectl get pods --field-selector spec.nodeName=<node_name> -o wide
```

Get detailed information about a Pod:
```
$ kubectl describe pod <pode_name>
```