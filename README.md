# mongo-cluster-docker

This is a simple 3 node replica mongodb setup based on official `mongo` docker image using `docker-compose`.

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

this should return something similar to:

```
--- Sharding Status --- 
  sharding version: {
	"_id" : 1,
	"minCompatibleVersion" : 5,
	"currentVersion" : 6,
	"clusterId" : ObjectId("587d306454828b89adaca524")
}
  shards:
  active mongoses:
	"3.4.1" : 1
  balancer:
	Currently enabled:  yes
	Currently running:  yes
		Balancer lock taken at Mon Jan 16 2017 22:18:53 GMT+0100 by ConfigServer:Balancer
	Failed balancer rounds in last 5 attempts:  0
	Migration Results for the last 24 hours: 
		No recent migrations
  databases:

```

# Reference

* https://github.com/senssei/mongo-cluster-docker.git
