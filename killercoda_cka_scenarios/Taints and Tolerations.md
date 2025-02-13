Run the command to list the taints applied to node01.

HINT: Use the kubectl command to describe the node


### Solution

#### list the Taints applied to node01
```
k desribe no node01 | grep Taints
```
The output should look similar to the following:

```
Taints:             dedicated=special-user:NoSchedule
```



View the file in your home directory named pod.yaml . Apply the correct toleration to this pod manifest in order for it to successfully get scheduled to node01.

After modifying the pod.yaml file, run the command k apply -f ~/pod.yaml to create the pod.

Then, run the command k get po -o wide to verify that the pod status is Running

HINT: The key, value, and effect have to match the taint


### Solution

The final pod.yaml file should look like this

```
apiVersion: v1
kind: Pod
metadata:
  labels:
    run: nginx
  name: nginx
spec:
  tolerations:
  - key: "dedicated"
    value: "special-user"
    effect: "NoSchedule"
  containers:
  - image: nginx
    name: nginx
```

