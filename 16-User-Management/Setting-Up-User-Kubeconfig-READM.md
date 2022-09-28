```
 610  openssl genrsa -out vagrant.pem 2048
  611  ls
  612  openssl x509 -req -in vagrant-csr.pem -CA /etc/kubernetes/pki/ca.crt -CAkey /etc/kubernetes/pki/ca.key -CAcreateserial -out vagrant.crt -days 100
  613  ls
  614  kubectl config set-cluster kubernetes --server=https://172.31.0.100:6443 --certificate-authority=/etc/kubernetes/pki/ca.crt --embed-certs=true  --kubeconfig=vagrant.kubeconfig
  615  ls
  616  cat vagrant.kubeconfig
  617  history
  618  kubectl config set-context vagrant@kubernetes --cluster=kubernetes --user=vagrant  --kubeconfig=vagrant.kubeconfig
  619  cat vagrant.kubeconfig
  620  kubectl config use-context vagrant@kubernetes   --kubeconfig=vagrant.kubeconfig
  621  cat vagrant.kubeconfig
  622  ls
  623  cat .kube/config
  624  cat vagrant.kubeconfig
  625  kubectl  get pods --kubeconfig=vagrant.kubeconfig
  626  cat vagrant.kubeconfig
  627  cp -rf vagrant.kubeconfig /home/vagrant/.kube/config
  628  chmod 777 /home/vagrant/.kube/config

```
