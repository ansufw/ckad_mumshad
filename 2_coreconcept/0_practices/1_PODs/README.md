# Question:

1. How many pods exist on the system?
2. Create a new pod with the nginx image.
3. How many pods are running now?
4. What is the image used to create the new pods?
5. Which nodes are these pods placed on?
6. How many containers are part of the pod webapp?
7. What images are used in the new webapp pod?
8. What is the state of the container agentx in the pod webapp?
9. Why do you think the container agentx in pod webapp is in error?
10. What does the READY column in the output of the kubectl get pods command indicate?
11. Delete the webapp Pod.
12. Create a new pod with the name myredis and the image redis123.
13. Now change the image redis123 on this myredis pod to redis.


# Answer:

1. run `kubectl get pods`
2. run `kubectl run nginx --image=nginx`
3. run `kubectl get pods`
4. run `kubectl describe pod [pod_name]`
5. run `kubectl describe pod [pod_name]`
6. run `kubectl describe pod [pod_name]` and check the containers section
7. run `kubectl describe pod [pod_name]` and check the containers section
8. run `kubectl describe pod [pod_name]` and check the containers section
9. a docker image is not available
10. all containers in the pod are ready
11. run `kubectl delete pod [pod_name]`
12. run `kubectl run myredis --image=redis123`
13. run `kubectl edit pod myredis` and change the image to redis



