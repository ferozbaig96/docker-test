# Pre-requisites
Have docker and k8s installed

# Run

```
kubectl create namespace nginx-proxy-namespace

kubectl -n nginx-proxy-namespace apply -f .

kubectl -n nginx-proxy-namespace get svc

curl <nginx-proxy-service-IP>:8090
```


# Delete resources

```kubectl delete namespaces nginx-proxy-namespace```
