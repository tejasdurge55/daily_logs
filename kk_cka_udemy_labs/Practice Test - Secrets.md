```
k get secrets 
k get secrets --no-headers
k get secrets --no-headers | wc -l
k describe secrets dashboard-token 
k get secrets 
k edit secrets dashboard-token 
```

create secret from CLI:
```
kubectl apply -f - <<EOF
apiVersion: v1
kind: Secret
metadata:
  name: db-secret
type: Opaque
data:
  DB_Host: $(echo -n "sql01" | base64 -w0)
  DB_User: $(echo -n "root" | base64 -w0)
  DB_Password: $(echo -n "password123" | base64 -w0)
EOF
```
```
vi pod.yaml
k apply -f pod.yaml 
k get po
k delete po webapp-pod --now
k apply -f pod.yaml 
history
```
