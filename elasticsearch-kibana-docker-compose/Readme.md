First generate elastic certificate p12 file
Google this how to generate certificate for elasticsearch
Update path of data nodes and certificate and then run any following command

docker-compose -f elasticsearch-kibana-password.yaml up -d
docker-compose -f elasticsearch-kibana-password.yaml down