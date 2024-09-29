# question
1. how to get list namespace?
    - run  `kubectl get namespace`
2. how to get pod list in the `research` namespace?
    - run `kubectl get pods --namespace research`
    - or run `kubectl get pods -n research`
3. Create a POD in the `finance` namespace with the name `redis` and the image `redis`.
    - run `kubectl run redis --image redis -n finance`
4. which namespace is the pod `blue` in?
    - run `kubectl get pods --all-namespaces`
5. Access the Blue web application using the link above your terminal!!



# command list