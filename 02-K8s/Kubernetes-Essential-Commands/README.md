# Kubernetes - Essential Commands

# Useful basic commands

### 1. Create a resource from a file or form stdin 
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

### 2. Delete resources by filename, stdin, resource and names or by resource label selector 
```
# Delete a pod using the type and name specified in pod.json.
kubectl delete -f ./pod.json

# Delete a pod based on the type and name in the JSON passed into stdin.
cat pod.json | kubectl delete -f -

# Delete pods and services with same names "baz" and "foo"
kubectl delete pod,service baz foo

# Delete pods and services with label name=myLabel.
kubectl delete pods,services -l name=myLabel

# Delete a pod with minimal delay
kubectl delete pod foo --now

# Force delete a pod on a dead node
kubectl delete pod foo --grace-period=0 --force

# Delete all pods
kubectl delete pods --all

#Delete all resources available in the folder.
kubectl delete -f <folder_name>
```

### 3. Edit a resource from the default editor
```
# Edit the service named 'docker-registry':
kubectl edit svc/docker-registry

# Use an alternative editor
KUBE_EDITOR="nano" kubectl edit svc/docker-registry

# Edit the job 'myjob' in JSON using the v1 API format:
kubectl edit job.v1.batch/myjob -o json

# Edit the deployment 'mydeployment' in YAML and save the modified config in its annotation:
kubectl edit deployment/mydeployment -o yaml --save-config
```

### 4. Expose a resource as a new Kubernetes service
```
# Create a service for a replicated nginx, which serves on port 80 and connects to the containers on port 8000.
kubectl expose rc nginx --port=80 --target-port=8000

# Create a service for a replication controller identified by type and name specified in "nginx-controller.yaml", which serves on port 80 and connects to the containers on port 8000.
kubectl expose -f nginx-controller.yaml --port=80 --target-port=8000

# Create a service for a pod valid-pod, which serves on port 444 with the name "frontend"
kubectl expose pod valid-pod --port=444 --name=frontend

# Create a second service based on the above service, exposing the container port 8443 as port 443 with the name "nginx-https"
kubectl expose service nginx --port=443 --target-port=8443 --name=nginx-https

# Create a service for a replicated streaming application on port 4100 balancing UDP traffic and named 'video-stream'.
kubectl expose rc streamer --port=4100 --protocol=udp --name=video-stream

# Create a service for a replicated nginx using replica set, which serves on port 80 and connects to the containers on port 8000.
kubectl expose rs nginx --port=80 --target-port=8000

# Create a service for an nginx deployment, which serves on port 80 and connects to the containers on port 8000.
kubectl expose deployment nginx --port=80 --target-port=8000

# Access Pod without exposing as service using kubectl --raw
kubectl get pod <pod_name> -o yaml|grep selfLink
kubectl get --raw <selfLink>:port/proxy/<filename>

```

### 5. Get - Display one or many resources
```
# List all pods.
kubectl get pods

# List all pods in ps output format with more information (such as node name).
kubectl get pods -o wide

# List a single replication controller with specified NAME in ps output format.
kubectl get replicationcontroller web

# List a single pod in JSON output format.
kubectl get -o json pod <pod-name>

# List a pod identified by type and name specified in "pod.yaml" in JSON output format.
kubectl get -f pod.yaml -o json

# Return only the phase value of the specified pod.
kubectl get -o template pod/<pod-name> --template=

# List all replication controllers and services together in ps output format.
kubectl get rc,services

# List one or more resources by their type and names.
kubectl get rc/web service/frontend pods/<pod-name>

# List all resources with different types.
kubectl get all
```

### 6. Run - Create and run a particular image, possibly replicated
```
# Start a single instance of nginx.
kubectl run nginx --image=nginx

# Start a single instance of hazelcast and let the container expose port 5701 .
kubectl run hazelcast --image=hazelcast --port=5701

# Start a single instance of hazelcast and set environment variables "DNS_DOMAIN=cluster" and "POD_NAMESPACE=default" in the container.
kubectl run hazelcast --image=hazelcast --env="DNS_DOMAIN=cluster" --env="POD_NAMESPACE=default"

# Start a single instance of hazelcast and set labels "app=hazelcast" and "env=prod" in the container.
kubectl run hazelcast --image=nginx --labels="app=hazelcast,env=prod"

# Start a replicated instance of nginx.
kubectl run nginx --image=nginx --replicas=5

# Dry run. Print the corresponding API objects without creating them.
kubectl run nginx --image=nginx --dry-run

# Start a single instance of nginx, but overload the spec of the deployment with a partial set of values parsed from JSON.
kubectl run nginx --image=nginx --overrides='{ "apiVersion": "v1", "spec": { ... } }'

# Start a pod of busybox and keep it in the foreground, don't restart it if it exits.
kubectl run -i -t busybox --image=busybox --restart=Never

# Start the nginx container using the default command, but use custom arguments (arg1 .. argN) for that command.
kubectl run nginx --image=nginx -- <arg1> <arg2> ... <argN>

# Start the nginx container using a different command and custom arguments.
kubectl run nginx --image=nginx --command -- <cmd> <arg1> ... <argN>

# Start the perl container to compute π to 2000 places and print it out.
kubectl run pi --image=perl --restart=OnFailure -- perl -Mbignum=bpi -wle 'print bpi(2000)'

# Start the cron job to compute π to 2000 places and print it out every 5 minutes.
kubectl run pi --schedule="0/5 * * * ?" --image=perl --restart=OnFailure -- perl -Mbignum=bpi -wle 'print bpi(2000)'
```






### The below are the list of essential commands that can be used to build images

|     Commands                 |    Description                                  |
| ------------------------------- | --------------------------------------------- |
| docker images | List all the images |
| docker build -t mywebapp:v1 .  | To build a custom image from Dockerfile |
| docker commit -m "comment" -p container-id new-image-name | Commit the container to build custom image |
| docker inspect image-id | Inspect the Image Details |
  
