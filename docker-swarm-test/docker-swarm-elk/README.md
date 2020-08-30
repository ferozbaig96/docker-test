# Pre-requisites
    1. Have docker and docker-compose installed
    2. Set the following on nodes that will be running Elasticsearch:
        1. Replace `OPTIONS=” — default-ulimit nofile=1024:4096"` with `OPTIONS=” — default-ulimit nofile=65536:65536" in `/etc/sysconfig/docker`
    3. Set the following on nodes that will be running Elasticsearch:
        1. `sysctl -w vm.max_map_count=262144`
        2. `echo 'vm.max_map_count=262144' >> /etc/sysctl.conf (to persist reboots)`

(2) and (3) are required to fix Error [1] and [2] respectively explained at the bottom.

# Run
```
docker stack deploy -c docker-compose.yml elk
```


Kibana Dashboard: Browse ip:5601

Can also configure filebeat in different clients and provide file-paths


# ERROR / FIX

### These errors can be found using
`docker service logs -f <elk_elasticsearch service name>`
`docker service logs -f elk_elasticsearch`


### ERROR:
[1]: max file descriptors [4096] for elasticsearch process is too low, increase to at least [65535]

### FIX:
https://medium.com/@borisdering/elasticsearch-as-a-service-on-docker-swarm-max-file-descriptors-error-c99f34572084

The file '/etc/sysconfig/docker' can be found using:
service docker status
    Loaded: loaded (/usr/lib/systemd/system/docker.service; ....
cat /usr/lib/systemd/system/docker.service

### ERROR:
[2]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]

### FIX:
Set the following on nodes that will be running Elasticsearch:
    1. `sysctl -w vm.max_map_count=262144`
    2. `echo 'vm.max_map_count=262144' >> /etc/sysctl.conf (to persist reboots)`

