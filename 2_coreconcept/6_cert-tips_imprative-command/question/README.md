# Question

1. deploy a pod with name nginx-pod using image nginx:alpine
    - answer: `kubectl run nginx-pod --image=nginx:alpine`
2. Deploy a redis pod using the redis:alpine image with the labels set to tier=db.
    - answer: `kubectl run redis --image=redis:alpine --labels=tier=db`
3. Create a service redis-service to expose the redis application within the cluster on port 6379.
    - answer: `kubectl expose pod redis --port=6379 --name redis-service`
4. Create a deployment named webapp using the image kodekloud/webapp-color with 3 replicas.
    - answer: `kubectl create deployment webapp --image=kodekloud/webapp-color --replicas=3`
5. Create a new pod called custom-nginx using the nginx image and run it on container port 8080.
    - answer: `kubectl run custom-nginx --image=nginx --port=8080`
6. Create a new namespace called dev-ns.
    - answer: `kubectl create namespace dev-ns`
7. Create a new deployment called redis-deploy in the dev-ns namespace with the redis image. It should have 2 replicas.
    - answer: `kubectl create deployment redis-deploy --image=redis --namespace=dev-ns --replicas=2`
8. Create a pod called httpd using the image httpd:alpine in the default namespace. Next, create a service of type ClusterIP by the same name (httpd). The target port for the service should be 80.
    - answer: `kubectl run httpd --image=httpd:alpine --expose=true --port=80`