# Pre-requisites
Have docker and docker-compose installed

Create webserver data directory in each node: 
```
$ mkdir -p /var/www/html
$ cp www/index.php /var/www/html/
```

Can also use any other centralized storage like AmazonS3/NFS/SSHfs etc.
Read more at https://docs.docker.com/storage/volumes/#share-data-among-machines
Rex-ray (container storage orchestration engine): https://github.com/rexray/rexray

# Run

```
$ docker stack deploy --compose-file docker-compose.yml nginxstack
```

```
$ curl localhost:8090
```

```
$ curl localhost:8090
```
