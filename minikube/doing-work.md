# Doing work

```bash
$ k create deployment echo --image=gcr.io/google_containers/echoserver:1.8
$ k get pods
$ k expose deployment echo --type=NodePort --port=8080
```

```bash
$ mk ip
$ k get service echo --output="jsonpath='{.spec.ports[0].nodePort}'"
$ $ curl http://192.168.99.103:31800/hi
```