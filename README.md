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

# kubectl - CLI utility
- tool used to deploy and manage applications on K8 cluster
 