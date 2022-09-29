```
1426  kubectl  create ns external
 1427  kubectl run pod-1 --image=amitvashist7/network-multitool
 1428  kubectl  get pods
 1429  kubectl run pod-2 --image=amitvashist7/network-multitool
 1430  kubectl run pod-3 --image=amitvashist7/network-multitool -n external
 1431  kubectl  get pods
 1432  kubectl  get pods -n external
 1433  kubectl  get pods -n external -o wide
 1434  kubectl  get pods  -o wide
 1435  kubectl exec -it pod-1 -- ping 192.168.189.125
 1436  kubectl exec -it pod-1 -- ping -c2 192.168.189.125
 1437  kubectl exec -it pod-1 -- ping -c2 192.168.235.174
 1438  kubectl exec -it pod-1 -- ping -c2 google.com
 1439  ls
 1440  cd 23-Ingress/
 1441  ls
 1442  cd ..
 1443  ls
 1444  mkdir 24-Network-Policy
 1445  cd 24-Network-Policy/
 1446  ls
 1447  vim 01-default-deny-ingress.yaml
 1448  kubectl  apply -f 01-default-deny-ingress.yaml
 1449  kubectl get netpol
 1450  kubectl  get pods  -o wide
 1451  kubectl  get pods  -n external -o wide
 1452  kubectl exec -it pod-1 -- ping -c2 google.com
 1453  kubectl exec -it pod-1 -- ping -c2 192.168.235.174
 1454  kubectl exec -it pod-3 -n external -- ping -c2 192.168.189.117
 1455  kubectl exec -it pod-2 -- ping -c2 192.168.189.117
 1456  kubectl exec -it pod-3 -- ping -c2 192.168.189.117
 1457  kubectl exec -it pod-3 -n external -- ping -c2 192.168.189.117
 1458  ls
 1459  > 01-default-deny-ingress.yaml
 1460  ls
 1461  vim 01-default-deny-ingress.yaml
 1462  kubectl  apply -f 01-default-deny-ingress.yaml
 1463  kubectl exec -it pod-3 -n external -- ping -c2 192.168.189.117
 1464  kubectl  get pods  -n external -o wide
 1465  kubectl  get pods  -o wide
 1466  kubectl exec -it pod-1 -- ping -c2 192.168.235.174
 1467  kubectl exec -it pod-2 -- ping -c2 192.168.235.174
 1468  kubectl exec -it pod-2 -- ping -c2 192.168.189.117
 1469  kubectl exec -it pod-3 -n external  -- ping -c2 192.168.189.117
 1470  kubectl exec -it pod-3 -n external  -- ping -c2 192.168.189.125
 1471  ls
 1472  vim 02-Allow-all-ingress.yaml
 1473  kubectl  delete -f 01-default-deny-ingress.yaml
 1474  kubectl  apply -f 02-Allow-all-ingress.yaml
 1475  kubectl exec -it pod-3 -n external  -- ping -c2 192.168.189.125
 1476  ls
 1477  kubectl  delete -f 02-Allow-all-ingress.yaml
 1478  vim 03-default-deny-egress.yaml
 1479  kubectl apply -f 03-default-deny-egress.yaml
 1480  kubectl exec -it pod-1 -- ping -c2 google.com
 1481  kubectl exec -it pod-2 -- ping -c2 google.com
 1482  kubectl exec -it pod-3 -n external  -- ping -c2 192.168.189.125
 1483  ls
 1484  kubectl  delete -f 03-default-deny-egress.yaml
 1485  vim 04-Allow-all-egress.yaml
 1486  kubectl  apply -f 04-Allow-all-egress.yaml
 1487  kubectl exec -it pod-3 -n external  -- ping -c2 192.168.189.125
 1488  ls
 1489  kubectl  delete -f 04-Allow-all-egress.yaml
 1490  vim 05-defualt-deny-all
 1491  kubectl  apply -f 05-defualt-deny-all
 1492  kubectl exec -it pod-3 -n external  -- ping -c2 192.168.189.125
 1493  kubectl exec -it pod-1   -- ping -c2 google.com
 1494  ls
 1495  mv 05-defualt-deny-all 05-defualt-deny-all.yaml
 1496  ls
 1497  vim 06-PodSelector.yaml
 1498  kubectl  delete -f 05-defualt-deny-all.yaml
 1499  kubectl  apply -f 06-PodSelector.yaml
 1500  kubectl  get pods  -o wide
 1501  kubectl  get pods -n external -o wide
 1502  kubectl exec -it pod-1   -- ping -c2 google.com
 1503  kubectl exec -it pod-2   -- ping -c2 google.com
 1504  kubectl exec -it pod-1   -- ping -c2 192.168.235.174
 1505  kubectl exec -it pod-3 -n external   -- ping -c2 192.168.189.117
 1506  kubectl  get pods --show-labels
 1507  kubectl label pod pod-1 role=suspicious
 1508  kubectl  get pods --show-labels
 1509  kubectl exec -it pod-1   -- ping -c2 192.168.235.174
 1510  kubectl exec -it pod-1   -- ping -c2 google.com
 1511  kubectl exec -it pod-2   -- ping -c2 google.com
 1512  kubectl  get pods -n external -o wide
 1513  kubectl  get pods -o wide
 1514  kubectl exec -it pod-3 -n external   -- ping -c2 192.168.189.117
 1515  kubectl exec -it pod-3 -n external   -- ping -c2 192.168.189.125
 1516  kubectl  get pods --show-labels
 1517  kubectl label pod pod-1 role-
 1518  kubectl  get pods --show-labels
 1519  kubectl exec -it pod-1   -- ping -c2 google.com
 1520  kubectl  delete -f 06-PodSelector.yaml
```
