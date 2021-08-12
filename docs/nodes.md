# Nodes

Following are the desired properties of a node
1. There are no leader and follower nodes. A flat hierarchy is to be followed.
2. Clear demarcation between node states and a well defined transition between them.
3. Daemonized node service falling under systemd.
4. Node-node communication as well as client-node communication is to be performed using messaging system.
5. Node state data store to be sublet to etcd.


## Node states:

* Mute node: A mute node has only one window of communication, i.e. cli. Other nodes cannot discover a mute node and nor can they communicate with it.

* Anxious node: An anxious node is deperate to find a family ( set of calm nodes which are hosting volumes ) or a group of calm nodes. The anxious node will subscribe to a node discovery channel topic to find other anxious nodes and also keep on sending its details to the discovery channel. This state is aimed at providing self discovery mechanism.

* Calm node: A calm node is similar to anxious node in functionality except that it doesn't send messages in a quick interval for finding a companion ( family or group of calm nodes ). A calm node can be made to connect with other nodes, through cli.

* Family node: A calm node which is part of a family of other calm nodes which are hosting a volume.

* Rude node: A rude node will reject incoming connect requests and won't connect with other nodes. But unlike mute nodes, other nodes can see this node in their surrounding.
