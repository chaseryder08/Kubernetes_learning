# KUBERNETES UDEMY COURSE / Notes

1) Install docker

<code>sudo apt-get install docker.io</code>

2) docker run hello-world
3) docker ps -a

<hr>

* Nodes (minions) - machine, physical or virtual where kubernetes installed

* node is worker machine where containers are launched by kybernetes

* cluster is group of nodes connected; having multiple nodes helps with sharing loads

* if node fails, can still work from other nodes, be accessible with other nodes in cluster

* master node - watches over nodes in cluster, and responsbile for orchestration of containers on worker nodes

## COMPONENTS:
api server - runs as front end of k8, all talk to api server to interact with cluster. 

etcd - stoires data to run cluster / multiple nodes/masters, etcd stores all info in cluster / implements logs, so no conflict

scheduler - distrbute work to multiple notes, assigns containers to nodes

controller - responds when nodes go down, bring up new containers

container runtime - softare used to run containerization - docker

kublet - agent run on each node in kluster, make sure containers are runnong on nodes as xpected

# WORKER and MASTER Nodes:

Master - has kube-apiserver, (makes master) 

Slave/worker - kublet agent (gives health information of nodes, and can received requests), container runtime (docker)

## kubectl - CLI utility
- tool used to deploy and manage applications on K8 cluster
 

## want to deploy app in form of containers, containers on set of machines (worker nodes) -- containers are encapsulated in POD - single instance of application 

### POD smallest object in kubernetes

### when more users are using application, create more pods that contain the instance;

### can also create new K8 node that holds another pod

### Pods have 1:1 relatinship with containers, tos cale up create new pods,or delete pods to scale down

### Pods can hold diff containers; helper container can work for application

//

# Kubectl
> how to deploy pods
## deploys docker container by creating pod - deploys instance of image --

## docker hub - public repo 

<code> kubectl run nginx --image nginx </code>

<code>kubectl get pods </code>
<code>kubectl describe pod nginx</code>
<code>kubectl get pods -o wide</code>

---

YAML

> xml vs json vs yaml

all used to store data

number of spaces for yaml is key

<code>

Fruits:
  - Orange
  - Apple
  - Bananna

</code>

# creating pod using YAML config file
K8 uses yaml for config file for pods

> required fields / root level properties in config file :

<code>
apiVersion: v1 (version of API - depending on what creating)
kind: Pod (type of object want to create)
metadata: (data about object)
    name: myapp-pod
    labels:
        app: myapp

spec:
</code>
