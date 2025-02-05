Create Countdown Job in Kubernetes
Create a job countdown-xfusion.

The spec template should be named as countdown-xfusion (under metadata), and the container should be named as container-countdown-xfusion

Use image fedora with latest tag only and remember to mention tag i.e fedora:latest, and restart policy should be Never.

Use command sleep 5

Note: The kubectl utility on jump_host has been configured to work with the kubernetes cluster.


```
apiVersion: batch/v1
kind: Job
metadata:
  name: countdown-xfusion
spec:
  template:
    metadata:
      name: countdown-xfusion
    spec:
      containers:
      - name: container-countdown-xfusion
        image: ubuntu:latest
        command: ["sleep",  "5"]
      restartPolicy: Never
```
