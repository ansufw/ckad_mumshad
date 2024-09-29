# KIND

how to install: https://kind.sigs.k8s.io/docs/user/quick-start/#installation

## Command

### create cluster
run `kind create cluster --config kind-example-config.yml --name my-cluster`

### delete cluster
run `kind delete cluster --name my-cluster`

### get all data

run `kubectl get all`

### get nodes

run `kubectl get nodes`

### get context list

run `kubectl config get-contexts`

### get cluster info

run `kubectl cluster-info`

### delete all container

run `docker rm -f $(docker ps -aq)`