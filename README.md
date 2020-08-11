# demo-docker-k8s-assignment

## Application Description
Demo app to show stateful behaviour of application.
Application is exposing hello controller which shows increase of counter value on each refresh of end point

## Application Logic 
* Spring boot hello controller has been exposed through url http://localhost:<node_port>/hello
* Logic is reading counter value from a file and increasing counter value and overriding file with updated value

##  K8S  Implementation 

* Kubenetes deployment is implemented using ReplicaSet of two pods.
* One example is created with empty dir volume which shows that counter values are not common for both pods, each pod is having their private copy of pod.
* Another example is cerated with persitent volume, which shows same copy of file is shared b/w pods and hence on each refresh of browser counter value will be increased.
* Node port is used for exposing service (LB implementation is not able to cover)

## Outputs 

kubectl get all 

kubectl get pv mypv-volume

kubectl get pvc mypv-claim

