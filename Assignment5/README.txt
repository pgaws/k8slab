
Spring Boot + MySQL on 3-Node Kubernetes Cluster Using Private Docker Image

STEP 1:
kubectl get nodes

STEP 2:
docker login

STEP 3:
docker tag springboot-app:v1 YOUR_DOCKER_ID/springboot-app:v1

STEP 4:
docker push YOUR_DOCKER_ID/springboot-app:v1

STEP 5:
Make Docker repository private from Docker Hub settings.

STEP 6:
kubectl create secret docker-registry regcred --docker-server=https://index.docker.io/v1/ --docker-username=YOUR_DOCKER_ID --docker-password=YOUR_PASSWORD --docker-email=YOUR_EMAIL

STEP 7:
kubectl apply -f configmap.yaml

STEP 8:
kubectl apply -f secret.yaml

STEP 9:
kubectl apply -f mysql-deployment.yaml
kubectl apply -f mysql-service.yaml

STEP 10:
Update app-deployment.yaml image name.

STEP 11:
kubectl apply -f app-deployment.yaml
kubectl apply -f app-service.yaml

STEP 12:
kubectl get pods -o wide

STEP 13:
kubectl get svc

STEP 14:
Access:
http://NODE-IP:NODEPORT/users
