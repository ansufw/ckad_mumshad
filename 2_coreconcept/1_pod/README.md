# Pods - Recapt

## Create a Pod 

### Command

- create pod `kubectl run [pod-name] --image=[image-name]:[image-version]`
- get pod list `kubectl get pods`
- forward pod network `kubectl port-forward [pod-name] [external-port]:[internal-port]`
- describe pod `kubectl describe pod [pod-name]`
- delete pod `kubectl delete pod [pod-name]`

**Practicing Commands**

```sh
# create nginx pod
kubectl run my-nginx --image=nginx:alpine

# check installed ponds and service/cluster
kubectl get pods
kubectl get services

# forward ip to nginx
kubectl port-forward my-nginx 9999:80

# check in the browser

# delete pod
kubectl delete pod my-nginx

# check pods
kubectl get pods

```

NOTE: k8s 1.8+ run only creates pod, k8s < 1.8 creates pod and other resources.


