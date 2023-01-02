###Install Elastic and Kibana using helm chart
https://phoenixnap.com/kb/elasticsearch-helm-chart

###Using ECK
Youtube video link -> https://www.youtube.com/watch?v=qjnT0pU0IRo
https://www.elastic.co/guide/en/cloud-on-k8s/2.5/k8s-deploy-kibana.html
1) Install crds  
 >> kubectl apply -f crds
check now
 > kubectl get kibana
 > kubectl get elasticsearch
 > kubectl get apmserver
 etc...
 
2) Install operators 
>> kubectl apply -f operator.yaml
> 
> kubectl get all -n elastic-system
  NAME                     READY   STATUS    RESTARTS   AGE
  pod/elastic-operator-0   1/1     Running   0          56s
  
  NAME                             TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)   AGE
  service/elastic-webhook-server   ClusterIP   10.110.237.5   <none>        443/TCP   56s
  
  NAME                                READY   AGE
  statefulset.apps/elastic-operator   1/1     56s

3) Install 3-elasticsearch.yaml

> kubectl apply -f .\efk\elasticsearch-kibana\3-elasticsearch.yaml
If you get image Init:ImagePullBackOff error then pull the image first and check the status of the pod. Delete/recreate the pod
For minikube -> minikube ssh docker pull imagename
For Dockerdesktop ->  docker pull imageName

To get the password of elastic user use following command
PASSWORD=$(kubectl get secret quickstart-es-elastic-user -o go-template='{{.data.elastic | base64decode}}')

kubectl port-forward service/quickstart-es-http 9200
curl -u "elastic:$PASSWORD" -k "https://localhost:9200"


Now Install Kibana using following command 

kubectl apply -f .\4-kibana.yaml
kubectl port-forward service/quickstart-kb-http 5601:5601
use elastic as username and password which is used for login to elasticsearch
