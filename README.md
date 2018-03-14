# cassandra

nodetool status
stutus    state                             tokens address 
up/down   normal/leaving/joining/moving     256

nodetool ring

data/conf/cassandra.yaml
num_tokens

To add a new node: 
docker inspect -f '{{ .NetworkSettings.IPAddress}}'  node1name
  127.0.0.7
docker run --name n2 -d cassandraimage -seeds 127.0.0.7
