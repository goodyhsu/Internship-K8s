## 1.工具安裝
`brew install minikube`
`brew install hyperkit`

### 測試是否安裝成功
* 在 cli 下 kubectl 指令，如果沒有被安裝：
`brew install kubectl`
* 運行 minikube
`minikube start --vm-driver=hyperkit`

## 2.Demo: Creation
* 查看現有的 Pod
`kubectl get pod`
* 創建 my-nginx Deployment
`kubectl create deployment my-nginx --image=nginx`
* 取得創建過程中發生的 event
`$ kubectl describe pod [pod name] | grep Events -A10`

## 3.Demo: Updating
* 更改 Pod container image 版本
`kubectl set image deployment/my-nginx nginx=nginx:stable-alpine`
* 查看現有的 Pod
`kubectl get pod`
* 取得 Pod image 版本
`$ kubectl describe pod [pod name] | grep image`

## 4.Demo: Failure
* 創建 2 replica 的 Deployment
`kubectl create deployment my-nginx-2replica --image=nginx --replicas=2`
* 查看現有的 Deployment 
`kubectl get deployments.apps`
* 查看現有的 Pod
`kubectl get pod`
* 刪除其中一個 Pod replica
`kubectl delete [pod name]`
* 取得 Deployment 發生的 event
`$ kubectl describe deployments.apps my-nginx-2replica | grep Events -A10`