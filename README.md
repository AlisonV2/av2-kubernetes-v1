# Alison Vandromme - Ynov M1 Docker Elective
Kubernetes - V1

## Stack 

<img src="https://img.shields.io/badge/kubernetes-326ce5.svg?&style=for-the-badge&logo=kubernetes&logoColor=white"/> <img src="https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white" /> <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" /> <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" /> <img src="https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E" /> <img src="https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white" />
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
### More on V2 :)