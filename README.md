# mongo-connector-docker
Dockerized Mongo Connector that uses volumes, a config file, and newer document manager. 
Automated build at dockerhub https://hub.docker.com/r/hibou/mongo-connector

- Provies elastic\_doc\_manager and elastic2\_doc\_manager
- Use /var/log/mongo-connector volume to store oplog
- Use /conf volume with config.json in it for configuration.

### Example

```
docker run -d \
  -v /path/data/mongo-connector:/var/log/mongo-connector \
  -v /path/conf/mongo-connector:/conf \
  --link some_elastic:elasticsearch \
  --link some_mongo:mongodb \
  hibou/mongo-connector
```
