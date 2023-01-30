```
  236  mkdir 04-Replication-Cantroller
  237  ls
  238  kubectl create rc --help
  239  kubectl create replicationcontroller test --help
  240  ls
  241  cd 04-Replication-Cantroller/
  242  ls
  243  vim 01-HelloWorld-RC.yaml
  244  ls
  245  cat 01-HelloWorld-RC.yaml
  246  ls
  247  kubectl  create -f 01-HelloWorld-RC.yaml --dry-run
  248  kubectl  get pods
  249  kubectl  get rc
  250  kubectl  create -f 01-HelloWorld-RC.yaml
  251  kubectl  get rc
  252  kubectl  get pods
  253  kubectl  get pods -o wide
  254  kubectl  delete pod helloworld-controller-k5w44 helloworld-controller-rpfr5
  255  kubectl  get pods -o wide
  256  kubectl scale --replicas=1 rc helloworld-controller
  257  kubectl  get rc
  258  kubectl  get pods -o wide
  259  kubectl scale --replicas=5 rc helloworld-controller
  260  kubectl  get pods -o wide
  261  ls
  262  cat 01-HelloWorld-RC.yaml
  263  ls
  264  kubectl  get pods
  265  kubectl  get pods -o wide
  266  kubectl delete pod --all
  267  kubectl  get pods -o wide
  268  kubectl delete pod --all
  269  ls
  270  kubectl  get rc
  271  kubectl api-resources
  272  ls
  273  cp -rf 01-HelloWorld-RC.yaml 02-HelloWorld-RC.yaml
  274  ls
  275  vim 02-HelloWorld-RC.yaml
  276  ls
  277  kubectl  apply -f 02-HelloWorld-RC.yaml
  278  kubectl  get rc
  279  kubectl  get pods
  280  kubectl  get pods -n kube-system
  281  ls
  282  cd ..
  283  ls
  284  kubectl  delete -f 04-Replication-Cantroller/
  285  kubectl  get pods
  286  ls
  287  cd ..
  288  ls
  289  git add .
  290  git commit -m "04-Replication-Cantroller"
  291  git push
  292  kubectl  get pods
  293  kubectl  get pods -o wide
  294  kubectl  run hello-k8s-2 --image=nginx --port=80
  295  kubectl  get pods
  296  ls
  297  cd 02-K8s/
  298  ls
  299  kubectl  apply -f 04-Replication-Cantroller/01-HelloWorld-RC.yaml
  300  kubectl  get pods
  301  kubectl  delete pod helloworld-controller-kc4m2
  302  kubectl  get pods
  303  kubectl delete pod hello-k8s-2
  304  kubectl  get pods
  305  kubectl  run hello-k8s-2 --image=nginx --port=80
  306  kubectl  get pods
  307  kubectl  get pods -A
  308  kubectl  get pods -A | grep -matser
  309  kubectl  get pods -A | grep -i -matser
  310  kubectl  get pods -A | grep -i -master
  311  kubectl  get pods
  312  kubectl  get pods -A | grep -i master
  313  systemctl  status kubelet
  314  ls
  315  cd /etc/kubernetes/
  316  ls
  317  cat kubelet.conf
  318  cat /var/lib/kubelet/config.yaml
  319  systemctl  status kubelet
  320  kubectl  run hello-k8s-2 --image=nginx --port=80
  321  kubectl  run hello-k8s-2 --image=nginx --port=80  --dry-run
  322  kubectl  run hello-k8s-2 --image=nginx --port=80  --dry-run -o yaml
  323  d
  324  cd
  325  watch -n .5 kubectl  get pods -o wide
```
