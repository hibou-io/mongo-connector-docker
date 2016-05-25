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

In theory, you don't need either volumes if you want to run it with the default config or 
for testing purposes. You can also issue your own command to run mongo-connector with CLI 
args instead of the config file.

### Compatability

I have tested this enough for my needs using the current mongo:3.2 (3.2.6) and 
elasticsearch:2 (2.3.3).
