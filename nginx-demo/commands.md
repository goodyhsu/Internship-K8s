# nginx demo
## 1. Tool Installation
* Install minikube to run a local K8s cluster<br>
`brew install minikube`
* Install hyperkit as minikube driver<br>
`brew install hyperkit`

### Testing
* Check if the tools have been installed correctly
* Run `kubectl` command on your cli, if it is not installed, please run `brew install kubectl`
* Start minikube<br>
`minikube start --vm-driver=hyperkit`

## 2.Demo: Creation
* Get pods in the cluster (in the default namespace)<br>
`kubectl get pod`
* Create my-nginx deployment<br>
`kubectl create deployment my-nginx --image=nginx`
* Get events that occurred during the creation of the pod<br>
`$ kubectl describe pod [pod name] | grep Events -A10`

## 3.Demo: Updating
* Change the container image version of the pod<br>
`kubectl set image deployment/my-nginx nginx=nginx:stable-alpine`
* Get pods in the cluster<br>
`kubectl get pod`
* Get the image version of the new pod<br>
`kubectl describe pod [pod name] | grep image`

## 4.Demo: Failure
* Create a deployment with 2 replicas<br>
`kubectl create deployment my-nginx-2replica --image=nginx --replicas=2`
* Get deployments in the cluster<br>
`kubectl get deployments.apps`
* Get pods in the cluste<br>
`kubectl get pod`
* Delete one of the replicas<br>
`kubectl delete pod [pod name]`
* Get events that occurred to the deployment<br>
`kubectl describe deployments.apps my-nginx-2replica | grep Events -A10`