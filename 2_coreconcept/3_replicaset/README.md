# Replication Controller

In this lecture, we will discuss about one controller in particular, and that is the replication controller. 

**So what is a replica and why do we need a replication controller?**

Let's go back to our first scenario where we had a single pod running our application. What if for some reason our application crashes and the pod fails?

Users will no longer be able to access our application. To prevent users from losing access to our application, we would like to have more than one instance or pod running at the same time. That way if one fails we still have our application running on the other one. The replication controller helps us run multiple instances of a single pod in the Kubernetes cluster thus providing high availability.    


**So does that mean you can't use a replication controller if you plan to have a single pod?**

**No.**

Even if you have a single pod the replication controller can help by automatically bringing up a new pod when the existing one fails.Thus, the replication controller ensures that the specified number of pods are running at all times even if it's just one or hundred.
Another reason we need replication controller is to create multiple pods to share the load across them. For example, in this simple scenario we have a single pod serving a set of users. When the number of users increase, we deploy additional pod to balance the load across the two pods.

If the demand further increases and if we were to run out of resources on the first node we could deploy additional parts across the other nodes in the cluster. As you can see, the replication controller spans across multiple nodes in the cluster. It helps us balance the load across multiple pods on different nodes as well as scale our application when the demand increases. It's important to note that there are two similar terms replication controller and replica set.

Both have the same purpose, but they're not the same. Replication controller is the older technology that is being replaced by replica set. Replica set is the new recommended way to set up replication. However, whatever we discussed in the previous few slides remain applicable to both these technologies.

There are minor differences in the way each works and we will look at that in a bit. As such, we will try to stick to replica sets in all of our demos and implementations going forward. Let us now look at how we create a replication controller. As with the previous lecture, we start by creating a replication controller definition file.