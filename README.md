# k8s pod info
The http server displays the IP address and the selected environment vars of the container serving the request.
Suitable for educational purposes e.g. verifying k8s load balancing concepts hands-on.

## Components
* config map
* deployment
* service

## Deploying
```
kubectl apply -f cm-indexphp.yaml
kubectl apply -f k8s-pod-info.yaml
```

## Usage
On a box which can access the cluster:
```bash
watch -n1 "curl -s IP:30001"
```
where `IP` is the address of one of the nodes.

In the browser you might need to use Ctrl+F5 to bypass caching.