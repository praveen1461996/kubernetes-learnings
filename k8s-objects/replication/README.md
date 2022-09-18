# What is Kubernetes replication for?


Before we go into the details on how you would do replication, let's talk about why.  
Typically you would want to replicate your containers (and thereby your applications) for several reasons, including:
## Reliability:
By having multiple versions of an application, you prevent problems if one or more fails.  This is particularly true if the system replaces any containers that fail.
Load balancing: Having multiple versions of a container enables you to easily send traffic to different instances to prevent overloading of a single instance or node. This is something that Kubernetes does out of the box, making it extremely convenient.
## Scaling: 
When load does become too much for the number of existing instances, Kubernetes enables you to easily scale up your application, adding additional instances as needed.


# Replication is appropriate for numerous use cases, including:
## Microservices-based applications: 
In these cases, multiple small applications provide very specific functionality.
## Cloud native applications: 
Because cloud-native applications are based on the theory that any component can fail at any time, replication is a perfect environment for implementing them, as multiple instances are baked into the architecture.
## Mobile applications:
Mobile applications can often be architected so that the mobile client interacts with an isolated version of the server application.


# ReplicationController Vs ReplicaSet:

 The major difference between a replication controller and replica set is that the rolling-update command works with Replication Controllers, but won't work with a Replica Set.  This is because Replica Sets are meant to be used as the backend for Deployments
