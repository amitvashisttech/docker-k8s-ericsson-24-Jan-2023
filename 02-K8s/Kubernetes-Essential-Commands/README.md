# Kubernetes - Essential Commands

# Useful basic commands

## Create a resource from a file or form stdin 
```
# Create a pod using the data in pod.json.
kubectl create -f ./pod.json

# Create a pod based on the JSON passed into stdin.
cat pod.json | kubectl create -f -

# Edit the data in docker-registry.yaml in JSON using the v1 API format then create
kubectl create -f docker-registry.yaml --edit --output-version=v1 -o json

# Create all the resources avaibale in the folder
kubeclt create -f <folder_name>
```



### The below are the list of essential commands that can be used to build images

|     Commands                 |    Description                                  |
| ------------------------------- | --------------------------------------------- |
| docker images | List all the images |
| docker build -t mywebapp:v1 .  | To build a custom image from Dockerfile |
| docker commit -m "comment" -p container-id new-image-name | Commit the container to build custom image |
| docker inspect image-id | Inspect the Image Details |
  
  
### The below are the list of essential commands that can be used with network

|     Commands                 |    Description                                  |
| ------------------------------- | --------------------------------------------- |
| docker network ls | List all the network |
| docker network inspect <network-id> | Inspect the Network Details |
| docker run -d --name myweb-9 -p 8080:9091 mywebapp:v6 | Static Port Mapping |
| docker run -d --name myweb-10 -P mywebapp:v6 | Dynamic Port Mapping |
| docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q) | List the container status & IP Details |
| docker exec -it container-id ifconfig | List the container status & IP Details |
| docker network create --driver "bridge" --subnet 172.28.0.0/16 --gateway 172.28.0.254 --ip-range 172.28.0.0/24 mybr0 | Create a custom Docker Network|  
| docker run -d --name container-name --network custom-network-name  imagename:tag | Binding a container to custom network|    
  
