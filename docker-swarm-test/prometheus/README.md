# Pre-requisites
Have docker and docker-compose installed

# Usage
First fix volume permissions:
``` 
$ sudo chown nfsnobody:nfsnobody -R /var/lib/docker/volumes/prometheus_data
```

```
$ docker stack deploy --compose-file docker-compose.yml prometheus
```
