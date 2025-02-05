# Practice Test - View Certificates
  
Solutions to practice test - view certificates
- Identify the certificate file used for the kube-api server
  
  <details>
  
  ```
  $ cat /etc/kubernetes/manifest/kube-apiserver.yaml
  
  Answer: /etc/kubernetes/pki/apiserver.crt
  ```
  </details>
  
- Identify the Certificate file used to authenticate kube-apiserver as a client to ETCD Server
  
  <details>
  ```
  $ cat /etc/kubernetes/manifest/kube-apiserver.yaml
  Answer: /etc/kubernetes/pki/apiserver-etcd-client.crt
  ```
  </details>
  
- Look for kubelet-client-key option in the file /etc/kubernetes/manifests/kube-apiserver.yaml
  
  <details>
  ```
  Answer: /etc/kubernetes/pki/apiserver-kubelet-client.key
  ```
  </details>
  
- Look for cert file option in the file /etc/kubernetes/manifests/etcd.yaml
  
  <details>
  ```
  Answer: /etc/kubernetes/pki/etcd/server.crt
  ```
  </details>
  
- Look for CA Certificate in file /etc/kubernetes/manifests/etcd.yaml
  
  <details>
  ```
  Answer: /etc/kubernetes/pki/etcd/ca.crt
  ```
  </details>
  
- Run the command openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text
  
  <details>
  ```
  $ openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text
  ```
  </details>
  
- Run the command openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text and look for issuer
  
  <details>
  ```
  $ openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text 
  ```
  </details>
  
- Run the command openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text and look at Alternative Names
  
  <details>
  ```
  $ openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text
  ```
  </details>
  
- Run the command openssl x509 -in /etc/kubernetes/pki/etcd/server.crt -text and look for Subject CN.
  
  <details>
  ```
  $ openssl x509 -in /etc/kubernetes/pki/etcd/server.crt -text
  ```
  </details>
  
- Run the command openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text and check on the Expiry date.
  
  <details>
  ```
  $ openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text
  ```
  </details>
  
- Run the command 'openssl x509 -in /etc/kubernetes/pki/ca.crt -text' and look for validity
  
  <details>
  ```
  $ openssl x509 -in /etc/kubernetes/pki/ca.crt -text
  ```
  </details>
  
- Inspect the --cert-file option in the manifests file.
  
  <details>
  ```
  $ vi /etc/kubernetes/manifests/etcd.yaml
  ```
  </details>
  
- ETCD has its own CA. The right CA must be used for the ETCD-CA file in /etc/kubernetes/manifests/kube-apiserver.yaml. 
  
  <details>
  ```
  View answer at /var/answers/kube-apiserver.yaml
  ```
  </details>






  



k describe po -n kube-system kube-apiserver-controlplane 
    4  k describe po -n kube-system kube-apiserver-controlplane | grep crt key
    5  k describe po -n kube-system kube-apiserver-controlplane | grep crt
    6  k describe po -n kube-system kube-apiserver-controlplane | grep -e 'key|crt'
    7  k describe po -n kube-system kube-apiserver-controlplane | grep -E 'key|crt'
    8* 
    9  k get po -A
   10  k describe po -n kube-system etcd-controlplane | grep -E 'key|crt'
   11  k describe po -n kube-system kube-apiserver-controlplane | grep crt
   12  openssl x509 -in /etc/kubernetes/pki/apiserver.crt -text -noout
   13  openssl x509 -in /etc/kubernetes/pki/etcd/ca.crt -text -noout
   14  openssl x509 -in /etc/kubernetes/pki/etcd/server.crt -text -noout
   15  openssl x509 -in /etc/kubernetes/pki/ca.crt -text -noout
   16  ci /etc/kubernetes/manifests/etcd.yaml
   17  vi /etc/kubernetes/manifests/etcd.yaml
   18  k apply -f /etc/kubernetes/manifests/etcd.yaml
   19  vi /etc/kubernetes/manifests/etcd.yaml
   20  k get po
   21  k apply -f /etc/kubernetes/manifests/etcd.yaml
   22  k get po
   23  k get po -A
   24  k get po
   25  docker ps
   26  crectl ps -a
   27  crictl ps -a
   28  crictl logs 9b278c3994170
   29  ls /etc/kubernetes/manifests/
   30  vi /etc/kubernetes/manifests/kube-apiserver.yaml 
   31  k apply -f /etc/kubernetes/manifests/kube-apiserver.yaml 
   32  crictl ps -a
   33  k apply -f /etc/kubernetes/manifests/kube-apiserver.yaml 
   34  crictl ps -a
   35  k get po
   36  crictl ps -a
   37  vi /etc/kubernetes/manifests/kube-apiserver.yaml 
   38  k apply -f /etc/kubernetes/manifests/kube-apiserver.yaml 
   39  crictl ps -a
   40  history

















