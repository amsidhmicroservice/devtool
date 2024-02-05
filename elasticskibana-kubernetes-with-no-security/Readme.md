First generate elastic certificate p12 file
Google this how to generate certificate for elasticsearch
Update path of data nodes and certificate and then run following command

kubectl apply -f elasticsearch.yaml
And
kubectl apply -f kibana.yaml