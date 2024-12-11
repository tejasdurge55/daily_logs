#### Identify the number of containers created in the red pod.
```
Use the command kubectl get pods and look at under the Ready section.
```

#### Identify the name of the containers running in the blue pod.
```
Use the command kubectl describe and identify the container name.
```

#### Create a multi-container pod with 2 containers.
#### Use the spec given below:
Name: yellow

Container 1 Name: lemon

Container 1 Image: busybox

Container 2 Name: gold

Container 2 Image: redis

#### If the pod goes into the crashloopbackoff then add the command sleep 1000 in the lemon container.
```
apiVersion: v1
kind: Pod
metadata:
  name: yellow
spec:
  containers:
  - name: lemon
    image: busybox
    command:
      - sleep
      - "1000"

  - name: gold
    image: redis
```

#### Edit the pod in the elastic-stack namespace to add a sidecar container to send logs to Elastic Search. Mount the log volume to the sidecar container.
#### details:
Name: app

Container Name: sidecar

Container Image: kodekloud/filebeat-configured

Volume Mount: log-volume

Mount Path: /var/log/event-simulator/

Existing Container Name: app

Existing Container Image: kodekloud/event-simulator

```
---
apiVersion: v1
kind: Pod
metadata:
  name: app
  namespace: elastic-stack
  labels:
    name: app
spec:
  containers:
  - name: app
    image: kodekloud/event-simulator
    volumeMounts:
    - mountPath: /log
      name: log-volume

  - name: sidecar
    image: kodekloud/filebeat-configured
    volumeMounts:
    - mountPath: /var/log/event-simulator/
      name: log-volume

  volumes:
  - name: log-volume
    hostPath:
      # directory location on host
      path: /var/log/webapp
      # this field is optional
      type: DirectoryOrCreate
```
