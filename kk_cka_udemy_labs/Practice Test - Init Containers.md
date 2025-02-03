  1  k apply -f ini
    2  ls
    3  vi sample.yaml 
    4  k apply -f sample.yaml 
    5  k edit po myapp-pod 
    6  vi sample.yaml 
    7  k apply -f sample.yaml 
    8  k get po 
    9  k edit po orange 
   10  k get po
   11  k edit po orange 
   12  k describe po orange -o yaml > pod.yaml
   13  k get po orange -o yaml > pod.yaml
   14  k delete po orange --now
   15  vi pod.yaml 
   16  k apply -f pod.yaml 
   17  k get po
   18  history

   
use kubectl describe mostly for solving everything in conjunction with grep

A new application orange is deployed. There is something wrong with it. Identify and fix the issue.


Once fixed, wait for the application to run before checking solution.
```
There is a typo in the command used by the initContainer. To fix this, first get the pod definition file by running kubectl get pod orange -o yaml > /root/orange.yaml.
Next, edit the command and fix the typo.
Then, delete the old pod by running kubectl delete pod orange
Finally, create the pod again by running kubectl create -f /root/orange.yaml
```

