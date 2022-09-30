## K8s Dashboard


### Install K8s Dashboard

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.4.0/aio/deploy/recommended.yaml
```

### Create a DashBoard Admin Service Account & Grant him ClusterAdminRole

```
kubectl  apply -f dash-admin-sa.yaml
kubectl  apply -f dash-admin-sa-binding.yaml
```

### Expose the Dashboard Service to NodePort
```
kubectl  get ns
kubectl get svc -n kubernetes-dashboard
kubectl edit svc kubernetes-dashboard -n kubernetes-dashboard
kubectl get svc -n kubernetes-dashboard
```

### Now try to open dashbaord url in the browser : https://NodeIP:NodePort


### Get the Admin Token to Authenticate with K8s Dashboard
```
kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep dashboard-admin | awk '{print $1}')
```

