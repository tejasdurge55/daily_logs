Schedule Cronjobs in Kubernetes:

The Nautilus DevOps team is setting up recurring tasks on different schedules. Currently, they're developing scripts to be executed periodically. To kickstart the process, they're creating cron jobs in the Kubernetes cluster with placeholder commands. Follow the instructions below:



Create a cronjob named nautilus.


Set Its schedule to something like */4 * * * *. You can set any schedule for now.


Name the container cron-nautilus.


Utilize the nginx image with latest tag (specify as nginx:latest).


Execute the dummy command echo Welcome to xfusioncorp!.


Ensure the restart policy is OnFailure.


Note: The kubectl utility on jump_host is configured to work with the kubernetes cluster.

```
kubectl create cj nautilus \
  --image=nginx:latest \
  --schedule="*/4 * * * *" \
  --restart=OnFailure \
  -- /bin/sh -c 'echo Welcome to xfusioncorp!'
```
then change container-name using
```
k edit cj nautilus
```

