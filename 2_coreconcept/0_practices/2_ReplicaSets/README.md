# Question
1. Delete any one of the 4 PODs.
    - run `kubectl get pods`
    - run `kubectl delete pod <pod-name>`
2. Delete the two newly created ReplicaSets - replicaset-1 and replicaset-2
    - run `kubectl delete replicasets replicaset-1 replicaset-2 `
3. Fix the original replica set new-replica-set to use the correct busybox image.
4. Scale the ReplicaSet to 5 PODs.
    - Use kubectl scale command or edit the replicaset using kubectl edit replicaset.

# Command List

## to know number of resources

```
kubectl get replicationcontroller
```

## to know number of pod created by rc

```
kubectl get pods
```

## to create rc from yaml file

```
kubectl create -f rc.yaml
```

## to delete rs
```
kubectl delete rs <rs-name>
```

## to edit rs
```
kubectl edit rs <rs-name>
```

## to scale rs
```
kubectl scale rs <rs-name> --replicas=<number>
```
