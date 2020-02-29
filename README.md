# Simple k8s service
The http server displays the IP address and the environment vars of the container serving the current request.
Suitable for educational purposes. It's helped me to understand how services work when learning k8s. It also can be helpful when understanding the difference between kubenet and Azure CNI network plugin in Azure Kubernetes Service.

## Components
* config map
* deployment
* service

## Deploying
```
kubectl apply -f hostinfo-cm.yaml
kubectl apply -f web.yaml
```

## Example usage
On a box which can access the cluster:
```
watch -n1 "curl -s 10.240.0.4:30001"
```
where the IP is your NodePort.