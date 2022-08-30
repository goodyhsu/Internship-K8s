all:
	kubectl apply -f mongo-configmap.yaml
	kubectl apply -f mongo-secret.yaml
	kubectl apply -f mongo-depl.yaml
	kubectl apply -f mongo-service.yaml
	kubectl apply -f mongo-express.yaml
	kubectl apply -f mongo-express-service.yaml
	kubectl apply -f mongo-ingress.yaml
	kubectl apply -f mongo-volume.yaml

clean:
	kubectl delete configmap mongodb-configmap
	kubectl delete secret mongodb-secret
	kubectl delete deployments.apps mongodb
	kubectl delete deployments.apps mongo-express
	kubectl delete service mongodb-service
	kubectl delete service mongo-express-service
	kubectl delete ingress mongo-ingress
	# kubectl delete volume
