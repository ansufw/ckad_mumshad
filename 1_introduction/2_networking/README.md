# Networking in K8s

- The node has an IP address. Say it is one 192.168.1.2
- On the single node kubernetes cluster, we have created a single pod
- a pod host a container but unlike in the Docker world where an IP address always assigned to a docker container.
- In the k8s world, the IP address is assigned to a pod.
- In this case, it's in the range ten point to 44 series and the IP assigned to the pod is 10.244.0.2.

![jpg](./single.svg)<img src="./single.svg">

- So how is it getting this IP address?
- When kubernetes is initially configured?
- We create an internal private network with the address `10.244.0.0` and all the ports are attached to it
- When you deploy multiple ports, they all get a separate IP assigned from this network. 