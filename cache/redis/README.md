

### Setting up a Redis Kubernetes Cluster
# Kindly refer the below link for step by step detail information

https://www.containiq.com/post/deploy-redis-cluster-on-kubernetes


Added new user in 4-redis-configmap.yaml file
as like below
user userredis allcommands allkeys on >Redis@123

Use this user for connecting to this redis cluster


The service endpoints for each Redis pod are given below:

#syntax
pod_name.service_name.namespace.svc.cluster.local

#Example
redis-0.redis.redis.svc.cluster.local  #This is master
redis-1.redis.redis.svc.cluster.local  This is salve
redis-2.redis.redis.svc.cluster.local  This is salve



