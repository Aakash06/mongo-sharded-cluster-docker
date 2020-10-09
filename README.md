# mongo-sharded-cluster-docker

This is a simple 2 replica set with 2 mongo node each MongoDb Sharded Cluster Setup based on official `mongo` docker image using `docker-compose`.

# Run

```
docker-compose -f docker-compose.1.yml -f docker-compose.2.yml  -f docker-compose.cnf.yml -f docker-compose.shard.yml up
```

# Tests

0. Core tests

Open mongo shell with one of the mongo node like mongo-1-1. Run 
```js
rs.status();
```

It will return `members` 3 nodes.

To check *sharding* status, Connect with *router* (mongos), `mongo-router` and Run:
```js
sh.status();
```

# Reference

* https://github.com/senssei/mongo-cluster-docker.git
