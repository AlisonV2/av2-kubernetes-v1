# Alison Vandromme - Ynov M1 Docker Elective - Kubernetes

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

### Step 3: 



