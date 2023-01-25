# Demo 1 

```
208  docker build -t mywebapp -f amit-file .
  209  docker run -d --name myweb-8 mywebapp
  210  docker ps
  211  docker inspect myweb-8 | grep -i ipaddress
  212  curl -v 172.17.0.9:8080
  213  curl -v 172.17.0.9:9091
  214  curl -v 172.17.0.9:9091/info.html
  215  ls
  216  curl -v 172.17.0.9:9091/info.html
  217  curl 172.17.0.9:9091/info.html
  218  docker ps
  219  docker kill $(docker ps -q)
  220  docker ps
  221  ip addr
  222  docker ps
  223  docker images
  224  docker inspect mywebapp:v6
  225  docker run -d --name myweb-9 -p 8080:9091 mywebapp:v6
  226  docker ps
  227  docker run -d --name myweb-9 -p 8080:9091 mywebapp:v6
  228  docker run -d --name myweb-10 -p 8080:9091 mywebapp:v6
  229  docker run -d --name myweb-11 -p 8081:9091 mywebapp:v6
  230  docker run -d --name myweb-12 -P mywebapp:v1
  231  docker run -d --name myweb-12 -P mywebapp:v6
  232  docker run -d --name myweb-13 -P mywebapp:v6
  233  docker ps
  234  docker run -d --name myweb-14 -P mywebapp:v6
  235  docker run -d --name myweb-15 -P mywebapp:v6
  236  docker ps
  237  docker run -d --name myweb-16 -P mywebapp:v5
  238  docker ps
  239  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)


  170  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
  171  curl 172.17.0.5:9091
  172  curl 172.17.0.5:9090
  173  netstat -tulnp
  174  systemctl  status docker
```


# Demo 2 

```
 206  systemctl status docker
  207  netstat -tulnp
  208  ip addr
  209  docker network ls
  210  bridge link
  211  ip addr
  212  docker network ls
  213  docker network create --help
  214  docker network create --driver "bridge" --subnet 172.28.0.0/16 --gateway 172.28.0.254 --ip-range 172.28.0.0/24 mybr0
  215  docker network ls
  216  docker network inspect mybr0
  217  history
  218  ip addr
  219  docker network ls
  220  docker kill $(docker ps -aq)
  221  docker rm $(docker ps -aq)
  222  ld
  223  docker network ls
  224  docker network rm mytest-br0
  225  docker network rm mybr0
  226  docker network ls
  227  docker network inspect none
  228  docker exec -it test-nw-1 ifconfig
  229  docker exec -it test-nw-w ifconfig
  230  docker exec -it test-nw-2 ifconfig
  231  docker exec -it test-nw-3 ifconfig

```
