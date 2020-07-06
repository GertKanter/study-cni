# Study CNI (Kubernetes)


## Getting Started
```bash
$ git clone https://github.com/rdbox-intec/study-cni.git
$ cd study-cni
$ kubectl apply -f manifest
deployment.apps/simulation-listener created
deployment.apps/simulation-roscore created
deployment.apps/simulation-talker created
service/simulation-roscore created

$ kubectl get pods
NAME                                   READY   STATUS    RESTARTS   AGE
simulation-listener-6976c99bd4-84729   1/1     Running   0          25m
simulation-roscore-5fcf5c9654-7wdfh    1/1     Running   0          25m
simulation-talker-6cffc7c7d4-k4t4s     1/1     Running   0          25m

$ kubectl logs simulation-listener-6976c99bd4-84729 -f
[INFO] [1594001173.025856]: /listenerI heard hello world 1594001173.024013
[INFO] [1594001173.125795]: /listenerI heard hello world 1594001173.124052
[INFO] [1594001173.226228]: /listenerI heard hello world 1594001173.2242084
[INFO] [1594001173.326462]: /listenerI heard hello world 1594001173.3246925
[INFO] [1594001173.425796]: /listenerI heard hello world 1594001173.4240358
[INFO] [1594001173.526164]: /listenerI heard hello world 1594001173.524595
[INFO] [1594001173.626199]: /listenerI heard hello world 1594001173.6245856
[INFO] [1594001173.726744]: /listenerI heard hello world 1594001173.724751
```


## 