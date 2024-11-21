```kubectl -n management logs --all-containers deploy/collect-data > /root/logs.log```

Tip:
```k -n management edit deploy collect-data```

Solution:
Delete one of the containers
```
spec:
  template:
    spec:
      containers:
      - image: nginx:1.21.6-alpine
        imagePullPolicy: IfNotPresent
        name: nginx
        resources: {}
        terminationMessagePath: /dev/termination-log
        terminationMessagePolicy: File
#      - image: httpd:2.4.52-alpine
#        imagePullPolicy: IfNotPresent
#        name: httpd
#        resources: {}
#        terminationMessagePath: /dev/termination-log
#        terminationMessagePolicy: File
```
