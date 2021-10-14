# Alison Vandromme - Ynov M1 Docker Elective
Kubernetes - V1

## Method used

### Step 1: Node Sample App Creation

- Created app.js with Node and Express
- Created a /error route to make the app crash on path match
- Tested the app in browser

### Step2: Dockerfile Creation

- Created Dockerfile
- Built and ran image with : 

```sh
docker build -f Dockerfile -t av2-docker-kub .
docker run -p 8080:8080 av2-docker-kub
```

### Step 3: Docker Hub Image Hosting

- Renamed local image
- Pushed it on Dockerhub to avoid ErrImagePull

```sh
docker tag av2-docker-kub alisonv2/docker-kub
docker push alisonv2/docker-kub
```

### Step 4: Deployment Creation

- Started cluster with Minikube
- Created deployment.yaml file with the image pushed on Dockerhub
- Applied deployment
- Checked deployments and pods

```sh
kubectl apply -f deployment.yaml
kubectl get deployments
kubectl get pods
```

### Step 5: Service Creation

- Created service.yaml file
- Checked if the service is ready
- Exposed Service with Minikube

```sh
kubectl apply -f service.yaml
kubectl get services
minikube service docker-kub-service
```

### Step 6: Config Files Merge

- Merged deployment and service files into one file

```sh
kubectl delete -f deployment.yaml,service.yaml
kubectl apply -f kubernetes.yaml
minikube service docker-kub-service
```
