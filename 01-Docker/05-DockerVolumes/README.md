# Docker Volumes Demo

```
375  mkdir 05-DockerVolumes
  376  docker ps
  377  docker kill $(docker ps -q)
  378  docker rm $(docker ps -q)
  379  docker rm $(docker ps -qa)
  380  ls
  381  docker run -it ubuntu:16.04
  382  docker ps
  383  docker ps -a
  384  docker start 4ab2a61732f1
  385  docker attach 4ab2a61732f1
  386  docker rm $(docker ps -qa)
  387  ls
  388  docker volume ls
  389  docker volume rm $(docker volume ls -q)
  390  docker volume ls
  391  docker volume create my-vol
  392  docker volume ls
  393  docker volume inspect my-vol
  394  cd /var/lib/docker/
  395  ls
  396  cd volumes/
  397  ls
  398  cd my-vol/
  399  ls
  400  cd _data/
  401  ls
  402  cd
  403  docker run -it -v my-vol:/myapp ubuntu:16.04
  404  docker ps
  405  docker inspect ad97bd604d07
  406  ls -ltr /var/lib/docker/volumes/my-vol/_data
  407  cat  /var/lib/docker/volumes/my-vol/_data/hello.txt
  408  hostname -f
  409  hostname -f >> /var/lib/docker/volumes/my-vol/_data/hello.txt
  410  date >> /var/lib/docker/volumes/my-vol/_data/hello.txt
  411  cat /var/lib/docker/volumes/my-vol/_data/hello.txt
  412  docker exec -it  ad97bd604d07 ls
  413  docker exec -it  ad97bd604d07 cat /myapp/hello.txt
  414  docker ps
  415  docker kill $(docker ps -q)
  416  docker rm $(docker ps -aq)
  417  docker ps -a
  418  docker volume ls
  419  cat /var/lib/docker/volumes/my-vol/_data/hello.txt
  420  docker ps
  421  docker images
  422  docker run -d --name test-apache-1 -v my-vol:/var/www/html/myapp -P mywebapp:v6
  423  docker ps
  424  docker run -d --name test-apache-2 -v my-vol:/var/www/html/myapp -P mywebapp:v6
  425  docker run -d --name test-apache-3 -v my-vol:/var/www/html/myapp -P mywebapp:v6
  426  docker ps
  427  cat /var/lib/docker/volumes/my-vol/_data/hello.txt
  428  > /var/lib/docker/volumes/my-vol/_data/hello.txt
  429  echo "Hey Docker Volume" >> /var/lib/docker/volumes/my-vol/_data/hello.txt
  430  docker volume ls
  431  docker volume rm my-vol
  432  docker run -d --name test-vol-demo-2 -v myvol1  -P mywebapp:v6
  433* docker run -d  -v /myvol1  -P mywebapp:v6
  434  docker run -d --name test-vol-demo-2-1 -v /myvol1  -P mywebapp:v6
  435  docker ps
  436  docker inspect test-vol-demo-2-1
  437  docker volume ls
  438  docker run -d --name test-vol-demo-2-2 -v /myvol1 -v /myapp -v /var/www/html/eric  -P mywebapp:v6
  439  docker inspect test-vol-demo-2-2
  440  docker ps
  441  echo "Hey Team Ericson" >> /var/lib/docker/volumes/912dc69d8a100105dfc19a62dff72806f241543a75f38406c0e6d862aedc1d5e/_data/index.html
  442  ls
  443  docker volume ls
  444  docker run -d --name test-vol-demo-3-1 -v /root/docker-k8s-ericsson-24-Jan-2023:/var/www/html/git  -P mywebapp:v6
  445  docker ps
  446  docker exec -it 47134e04de51 bash
  447  docker run -d --name test-vol-demo-3-2 -v /root/docker-k8s-ericsson-24-Jan-2023:/var/www/html/git:ro  -P mywebapp:v6
  448  docker ps
  449  docker exec -it test-vol-demo-3-2 bash
  450  docker inspect test-vol-demo-3-2
  451  docker exec -it test-vol-demo-3-2 bash
  452  ls

```
