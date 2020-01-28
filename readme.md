# Container things.  

### Running your own docker registry
Downlaod registry image from docker hub 
```
$ docker run -d -p 5000:5000 --restart=always --name registry registry:2
``` 
Tag your local images 

```
$ docker image tag ubuntu localhost:5000/myfirstimage
```
Push it 
```
$ docker push localhost:5000/myfirstimage
```
Pull it back
```
$ docker pull localhost:5000/myfirstimage
```

### Kubernates 

Get nodes

```
$ kubectl get nodes
NAME                      STATUS  AGE  VERSION
gke-kubia-85f6-node-0rrx  Ready   1m    v1.5.3
gke-kubia-85f6-node-heo1  Ready   1m    v1.5.3
gke-kubia-85f6-node-vs9f  Ready   1m    v1.5.3
```


Describe node 
```
$ kubectl describe node <node_name>
```
Describe pod
```
$ kubectl describe pods <podname>
```

Delete multiple pods by name 
```
$ kubectl get pods | grep kubia | awk '{print $1}' | xargs kubectl delete pod
```
