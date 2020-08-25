# Pre-requisites

Have docker and docker-compose installed

# Usage

```
$ docker-compose  --compatibility up -d
```

--compatibility option is used to let docker scale the service in the same node. Otherwise, deploy.replicas is used for swarm mode. Hence must be used with ```docker stack deploy```

