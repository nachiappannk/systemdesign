# MongoDB

1. support sharding out of the box
2. Need to connect via mongos for sharded cluster
3. Each shard could be replicated for high availability
4. The write can specify the number of replicas that should succeed
5. The read can specify if it has to come from primary, secondary or minimum latency
6. There is a collection called operation logs for the replication part
