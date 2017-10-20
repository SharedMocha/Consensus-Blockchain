# Consensus in Hyperledger

Consensus may be implemented in different ways such as through the use of 
1.)Lotterybased algorithms including Proof of Elapsed Time (PoET) and Proof of Work (PoW) or
2.)Voting-based methods including Redundant Byzantine Fault Tolerance
(RBFT) and Paxos.

Each of these approaches targets different network requirements and fault tolerance models.

The lottery-based algorithms are advantageous in that they can scale to a large number of nodes since the winner of the lottery proposes a block and transmits it to the rest of the network for validation. On the other hand, these algorithms may lead to forking when two “winners” propose a block. Each fork must be resolved, which results in a longer time to finality.

The voting-based algorithms are advantageous in that they provide low-latency finality. When a majority of nodes validates a transaction or block, consensus exists and finality occurs. Because voting-based algorithms typically require nodes to transfer messages to each of the other nodes on the network, the more nodes that exist on the network, the more time it takes to reach consensus. This results in a trade-off between scalability and speed.


| Framework | Consensus Algorithm | Advantages |
| :---         |     :---:      |          ---: |
| Fabric   | Kafka     | Provides crash fault
tolerance. Finality
happens in a matter of
seconds.    |
| Indy     | RBFT      | Provides Byzantine
fault tolerance. Finality
happens in a matter of
seconds.     |
| Iroha   | Sumeragi     | Provides Byzantine
fault tolerance. Finality
happens in a matter
of seconds. Scale to
petabytes of data,
distributed across many
clusters (Struckhoff, 2016).    |
| Sawtooth     | PoET      | Provides scalability and
Byzantine fault tolerance.   |
