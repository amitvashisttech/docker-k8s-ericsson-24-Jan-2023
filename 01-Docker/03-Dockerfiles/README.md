# Create a new Docker Image, Run as Container 


## Step-1: Create Dockerfile
- **Dockerfile**
```
FROM nginx
COPY index.html /usr/share/nginx/html
```

## Step-2: Build Docker Image & run it
```
docker build -t mywebapp:v1 .
docker run  -d --name test-webapp-1 mywebapp:v1
```

## Step-3: Check the Container IP & Access the Web Page
```
docker inspect <container-id>
curl -v <container-ip>
```

