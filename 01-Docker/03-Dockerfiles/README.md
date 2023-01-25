# Create a new Docker Image, Run as Container 


## Step-1: Create Dockerfile
- **Dockerfile**
```
#  Base Image 
FROM ubuntu:16.04

# Who's the maintainer
MAINTAINER Amit Vashist <amitvashist7@outlook.com>

# Update the APT Repo 
RUN apt-get update 

# Install Apache Packages 
RUN apt-get install apache2 -y 

# Bring Up Apache Service
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND" ]
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

