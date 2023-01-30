```
371  cd 06-Service/
  372  ls
  373  cat 01-helloworld.yaml
  374  ls
  375  kubectl  apply -f 01-helloworld.yaml
  376  kubectl get pods
  377  kubectl  delete -f 01-helloworld.yaml
  378  kubectl  apply -f 01-helloworld.yaml
  379  kubectl get pods
  380  ls
  381  kubectl  get rc
  382  kubectl get pods
  383  kubectl delete pod helloworld-controller-5s99k helloworld-controller-nd4rv helloworld-controller-qdwwh --force
  384  ls
  385  kubectl get pods
  386  cat 01-helloworld.yaml
  387  vim 01-helloworld.yaml
  388  kubectl get pods
  389  ls
  390  kubectl  get pods
  391  cat 01-helloworld.yaml
  392  kubectl  apply -f 01-helloworld.yaml
  393  kubectl  get pods
  394  vim 01-helloworld.yaml
  395  kubectl  get pods
  396  kubectl  apply -f 01-helloworld.yaml
  397  kubectl  get pods
  398  kubectl  delete  -f 01-helloworld.yaml
  399  kubectl  get pods
  400  kubectl  apply -f 01-helloworld.yaml
  401  ls
  402  kubectl  get rc
  403  vim 01-helloworld.yaml
  404  kubectl  apply -f 01-helloworld.yaml
  405  kubectl  get pods -o wide
  406  kubectl  get svc
  407  ls
  408  vim 02-helloworld-svc.yaml
  409  kubectl  apply -f 02-helloworld-svc.yaml
  410  kubectl  get svc
  411  cat 02-helloworld-svc.yaml
  412  kubectl  get svc
  413  kubectl describe svc helloworld-service
  414  kubectl  get pods -o wide
  415  kubectl  get pods --show-labels
  416  kubectl scale --replicas=1 rc helloworld-controller
  417  kubectl  get pods --show-labels
  418  kubectl  get pods -o wide
  419  kubectl describe svc helloworld-service
  420  kubectl scale --replicas=2 rc helloworld-controller
  421  kubectl describe svc helloworld-service
  422  kubectl  get pods -o wide
  423  kubectl  get pods --show-labels
  424  kubectl get svc
  425  kubectl get pods
  426  kubectl get svc
  427  kubectl  get pods -o wide
  428  cd
  429  ;s
  430  ls
  431  cd docker-k8s-ericsson-01-Dec-2022/
  432  ls
  433  cd 02-K8s/
  434  ls
  435  vim 00-Setup/install-k8s-master-node.sh
  436  kubectl  get pods -n kube-system
  437  vim 00-Setup/install-k8s-master-node.sh
  438  kubectl  get pods -n kube-system
  439  kubectl  get pods -n kube-system -o wide
  440  kubectl get pods -o wide
  441  kubectl  get svc
  442  kubectl describe svc helloworld-service
  443  ls
  444  cd 06-Service/
  445  ls
  446  kubectl  get svc
  447  ls
  448  vim 03-app-svc-deployment.yaml
  449  kubectl  apply -f 03-app-svc-deployment.yaml
  450  kubectl  get svc
  451  kubectl  get pods
  452  kubectl  describe svc python-webapp-svc
  453  kubectl  get pods -o wide
  454  kubectl  get pods --show-labels
  455  ls
  456  cat 03-app-svc-deployment.yaml
```
