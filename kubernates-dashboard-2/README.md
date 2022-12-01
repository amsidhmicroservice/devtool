##### ###This is working Kubernetes Dashboard Example###

# https://andrewlock.net/running-kubernetes-and-the-dashboard-with-docker-desktop/

## For installing

### kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

### kubectl apply -f kubernates-dashboard-2/2-dashboard-adminuser.yaml

kubectl proxy
URL -> http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
Now create the token for login token based login in above url.

### https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md

Following command requires kubectl client and server version required to be greated than v1.24.0. 
kubectl -n kubernetes-dashboard create token admin-user
    Note- To check the kubectl running version use command 'kubectl version -o json'
    check clientVersion.gitVersion and serverVersion.gitVersion in json output


## For uninstalling

### kubectl delete -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

### https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md