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


# Snitch
A snitch determines which datacenters and racks nodes belong to. They inform Cassandra about the network topology so that requests are routed efficiently and allows Cassandra to distribute replicas by grouping machines into datacenters and racks. 

USed to effficiently route requests.
The replication strategy places the replicas based on the information provided by the new snitch. 
All nodes must return to the same rack and datacenter. Cassandra does its best not to have more than one replica on the same rack (which is not necessarily a physical location).

SimpleSnitch
  The SimpleSnitch is used only for single-datacenter deployments.
RackInferringSnitch
   Determines the location of nodes by rack and datacenter corresponding to the IP addresses.
PropertyFileSnitch
  Determines the location of nodes by rack and datacenter.
GossipingPropertyFileSnitch
  Automatically updates all nodes using gossip when adding new nodes and is recommended for production.
Ec2Snitch
  Use the Ec2Snitch with Amazon EC2 in a single region.
Ec2MultiRegionSnitch
  Use the Ec2MultiRegionSnitch for deployments on Amazon EC2 where the cluster spans multiple regions.
GoogleCloudSnitch
  Use the GoogleCloudSnitch for Cassandra deployments on Google Cloud Platform across one or more regions.
CloudstackSnitch
  Use the CloudstackSnitch for Apache Cloudstack environments.
  
docker run --name n2 -d cassandraimage -dc dc1 -rack rak1
  
  
