<p align="center">
  <img width="260" src="https://storage.googleapis.com/my-newest-bucket-coinsparta/compose.png" alt="Docker Compose sample file">
</p>


# Docker Compose Examples:
Simple Docker compose examples to bootstrap your project needs.  












#### MongoDB Master-Replica Example:
---
##### Fetch file:
```
curl https://raw.githubusercontent.com/mariothedev/docker-compose-examples/master/docker-compose.yml --output docker-compose.yml
```
```
version: "3"
services:
  mongo0:
    hostname: mongo0
    image: mongo
    ports:
      - 27017:27017
    restart: always
    entrypoint: [ "/usr/bin/mongod", "--bind_ip_all", "--replSet", "rs0" ]
  mongo1:
    hostname: mongo1
    image: mongo
    ports:
      - 27018:27017
    restart: always
    entrypoint: [ "/usr/bin/mongod", "--bind_ip_all", "--replSet", "rs0" ]
  mongo2:
    hostname: mongo2
    image: mongo
    ports:
      - 27019:27017
    restart: always
    entrypoint: [ "/usr/bin/mongod", "--bind_ip_all", "--replSet", "rs0" ]
  redis0:
    image: redis
    ports: 
      - 6379:6379
```


#### Persistent Redis Example:
---
##### Fetch file:
```
curl https://raw.githubusercontent.com/mariothedev/docker-compose-examples/master/docker-compose.yml --output docker-compose.yml
```
```
  redis0:
    image: redis
    ports: 
      - 6379:6379
    restart: always
    entrypoint: redis-server --appendonly yes
```
