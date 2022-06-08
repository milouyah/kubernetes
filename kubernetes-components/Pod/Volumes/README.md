# [Volumes](https://kubernetes.io/docs/concepts/storage/volumes/)

* emptyDir - 일시적인 데이터를 저장하는데 사용되는 간단한 빈 디렉토리
* hostPath - worker node의 파일시스템을 파드의 디렉토리로 마운트하는데 사용한다.
* gitRepo
* nfs
* gcePersistentDisk, awsElasticBlockStore, azureDisk
* cinder, cephfs, iscsi, flocker,glusterfs, quobyte, rbd, flexVolue, vsphereVloume, photonPersitentDisk, scaleIO
* `configMap`, `secret`, `downwardAPI`
* persistentVolumeClaim


## emptyDir

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: fortune
spec:
  containers:
  - image: luksa/fortune
    name: html-generator
    volumeMounts:
    - name: html
      mountPath: /var/htdocs
  - image: nginx:alpine
    name: web-server
    volumeMounts:
    - name: html
      mountPath: /usr/share/nginx/html
      readOnly: true
    ports:
    - containerPort: 80
      protocol: TCP
  volumes:
  - name: html
    emptyDir: {}
```

## gitRepo
* 기본적으로 emptyDir
* 



