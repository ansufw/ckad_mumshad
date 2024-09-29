# Commands

## See status rollout

1. run `kubectl create -f deployment-definition.yaml`
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp-deployment
  labels:
    tier: frontend
spec:
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      name: nginx-2
      labels:
        app: myapp
    spec:
      containers:
        - name: nginx
          image: nginx
  replicas: 6
  ```
2. run `kubectl rollout status myapp-deployment` 

## See History rollout

3. delete the the deployment `kubectl delete deployment myapp-deployment`
4. now using record, re-create the deployment `kubectl create -f deployment-definition.yaml --record`
5. run to see history of deployment, `kubectl rollout history myapp-deployment`
6. confirm the config `kubectl describe deployment myapp-deployment` and see on the Annotations section

## Update pods and check the status

7. edit deployment `kubectl edit deployment myapp-deployment --record`
8. check the status `kubectl rollout status myapp-development` and see the update between new and old replicas
9. check the history `kubectl rollout history deployment.apps/myapp-deployment`
10. edit image deployment `kubectl set image deployment myapp-deployment nginx=nginx:1.27 --record`

## Undo pod update 

11. run `kubectl rollout undo deployment myapp-deployment`
12. check history `kubectl rollout history deployment myapp-deployment`, and you shall see the previous revision (no.3) pushed into the latest (no.5)
```
REVISION  CHANGE-CAUSE
1         <none>
2         <none>
4         kubectl set image deployment myapp-deployment nginx=nginx:1.27 --record=true
5         kubectl edit deployment myapp-deployment --record=true
```

## Fail rollback update

13. run `edit` command for the deployment and change the image to something doesn't exist like `nginx:1.27-gogogo`
14. run `kubectl rollout status deployment myapp-deployment` and see what happen, the result not succeed
15. cancel and run another command, `kubectl get deployment myapp-deployment`
16. check pods, `kubectl get pods`
17. run undo command: `kubectl rollout undo deployment myapp-deployment`