# Pre-requisites
Have docker and k8s installed

# Run

```
kubectl create namespace static-vol-namespace
kubectl -n static-vol-namespace apply -f pv-example.yml
kubectl -n static-vol-namespace apply -f pvc-example.yml
kubectl -n static-vol-namespace apply -f pod-with-pvc.yml
kubectl -n static-vol-namespace get pod -o wide

curl <podIP>:80

```

Data will be fetched from node's (worker node) pv built from "/mnt/data" directory

# Delete resources

Delete sequence: pod, pvc, pv

```
kubectl delete pod my-pvc-pod -n static-vol-namespace
kubectl delete pvc my-pv-claim -n static-vol-namespace
kubectl delete pv my-pv-volume -n static-vol-namespace
kubectl delete namespaces static-vol-namespace
```

OR

```kubectl delete namespaces static-vol-namespace```
