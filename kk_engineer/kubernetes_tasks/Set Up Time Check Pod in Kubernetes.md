The DevOps team want to create a time check pod in a particular Kubernetes namespace and record the logs. This might be initially used only for existing purposes, but later can be implemented in a n existing cluster. Please find more details beow about the task and perform it.
Create a pod called time-check in the devops namespace. This pod should run a container called time-check container should use the busybox image with latest tag only and remember to mention tag i.e busybox:latest.
Create a config map called time-config with the data TIME_FREQ=10 in the same namespace, and volume name should be log-volume.
The time-check container should run the command: while true; do date; sleep $TIME_FREQ;done and should write the result to the location /opt/security/time/time-check.log.
The path /opt/security/time on the pod should mount a volume that lasts the lifetime of this pod.


```
k create cm time-config --from-literal=TIME_FREQ=8 -n xfusion 
```

```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: log-volume-persistent
  labels:
    type: local
spec:
  storageClassName: manual
  capacity:
    storage: 10Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: "/opt/security/time"

---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: task-pv-claim
  namespace: xfusion
spec:
  storageClassName: manual
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 3Gi
```

```
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: time-check
  name: time-check
  namespace: xfusion
spec:
  volumes:
    - name: log-volume
      persistentVolumeClaim:
        claimName: task-pv-claim
  containers:
  - image: busybox:latest
    volumeMounts:
        - mountPath: "/opt/security/time"
          name: log-volume
    command: [ "/bin/sh", "-c", "while true; do date; sleep $TIME_FREQ;done > /opt/security/time/time-check.log" ]
    env:
        - name: TIME_FREQ
          valueFrom:
            configMapKeyRef:
              name: time-config
              key: TIME_FREQ

    name: time-check
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```
