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

# Start a new ubuntu:16.04 based container & install net-tools by running the following commands
```
'apt-get update ; apt-get install net-tools -y' 
```
# Now come out of the container by following Escap Seq -> CTL P Q. 
# Finally commit the container & create a nework image. 
```

```
docker commit -m "My Network" -p test-nw-1 mynetwork:v1
```


  264  docker run -it --name test-nw-1 ubuntu:16.04
  265  docker ps
  266  docker commit -m "My Network" -p test-nw-1 mynetwork:v1
  267  docker ps
  268  docker images
  269  docker commit -m "My Network" -p test-nw-1 mynetwork:v1
  270  docker ps
  271  docker kill $(docker ps -q)
  272  docker rm $(docker ps -q)
  273  docker rm $(docker ps -qa)
  274  docker ps -a
  275  docker ps
  276  docker images
  277  docker run -itd --name test-nw-1 mynetwork:v1
  278  docker ps
  279  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
  280  docker exec -it $(docker ps -q) ifconfig
  281  docker exec -it $(docker ps -q) route n
  282  docker exec -it $(docker ps -q) route -n
  283  docker exec -it $(docker ps -q) ifconfig
  284  docker network ls
  285  docker exec -it $(docker ps -q) route -n
  286  docker network inspect bridge
  287  ls
  288  docker network  ls
  289  docker exec -it $(docker ps -q) route -n
  290  docker network create --help
  291  docker network create mytest-br0
  292  docker network  ls
  293  docker network  inspect mytest-br0
  294  docker run -itd --name test-nw-2 mynetwork:v1
  295  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
  296  docker run -itd --name test-nw-3 mynetwork:v1
  297  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
  298  docker run -itd --network mytest-br0 --name test-nw-4 mynetwork:v1
  299  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
  300  docker run -itd -network mytest-br0 --name test-nw-5 mynetwork:v1
  301  docker run --help
  302  docker run --help | grep -i network
  303  docker run -itd --name test-nw-6 --network mytest-br0 mynetwork:v1
  304  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
  305  docker ps
  306  docker inspect test-nw-4
  307  docker inspect test-nw-5
  308  docker inspect test-nw-6
  309  docker exec -it $(docker ps -q) route -n
  310  docker ps
  311  docker exec -it test-nw-1 route -n
  312  docker exec -it test-nw-6 route -n
  313  docker network ls
  314  docker network inspect mytest-br0
  315  docker run -itd --name test-nw-7 --network mytest-br0 --network docker0 mynetwork:v1
  316  docker network ls
  317  docker run -itd --name test-nw-8 --network mytest-br0 --network bridge mynetwork:v1
  318  docker ps
  319  docker exec -it test-nw-8 route -n
  320  docker exec -it test-nw-8 ifconfig
  321  docker run -itd --name test-nw-9 --network mytest-br0 -p 9095:9090 mynetwork:v1
  322  docker ps
  323  docker images
  324  docker run -d --name test-nw-10 --network mytest-br0 -P mywebapp:v6
  325  docker ps
  326  docker inspect --format '{{.Name}} {{.State.Running}} {{.NetworkSettings.IPAddress}}' $(docker ps -q)
  327  docker inspect test-nw-10
  328  docker ps
  329  curl 172.18.0.5:9091
  330  docker run -d --name test-nw-12 --network mybr0 -P mywebapp:v6
  331  docker run -d --name test-nw-13 --network mybr0 -P mywebapp:v6
  332  docker run -d --name test-nw-14 --network mybr0 -P mywebapp:v6
  333  docker exec -it test-nw-14 ifconfig
  334  docker run -d --name test-nw-15 --network mybr0 -P mynetwork:v1
  335  docker run -itd --name test-nw-16 --network mybr0 -P mynetwork:v1
  336  docker ps
  337  docker exec -it test-nw-16 ifconfig
  338  docker exec -it test-nw-16 route -n
  339  docker run -itd --name test-nw-1 --network none  mynetwork:v1
  340  docker run -itd --name test-nw-2 --network none  mynetwork:v1
  341  docker run -itd --name test-nw-3 --network host  mynetwork:v1
  342  docker network ls
  343  docker run -itd --name test-nw-4 --network host  mywebapp:v6
  344  docker ps
  345  netstat -tulnp
  346  docker run -itd --name test-nw-5 -P   mywebapp:v6
```


# Demo 3

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
