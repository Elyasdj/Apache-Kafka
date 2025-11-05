# Apache-Kafka - Complete Setup Guide


What is Kafka? It like post-office (that seat in the middle)

Is Kafka a Replacement for Database? Simple answer is no

Real-time Processoing (Streams API) : 
    Use case : 1- Real-time Metrics
               2- Personalized Recommendations
               3- website Activity Tracking
               4- Fraud Detection

Partitions for Scalability and  Performance : 
Consumer Group for Scalable Message Consumption :
*tip: Kafka distributes load automatically.

What is Broker?
    Server that store data (message) in topics, manages message distribution to consumers.
Fault Tolerance
    Topic's partitions are distributed across multiple broker.
    Each partition has a leader broker and multiple replicas.

Kafka vs RabbitMQ/ActiveMQ
Kafka -> Store message on disk for a configurable retention period
      -> Also optimized for high-throughput

RabbitMQ/ActiveMQ -> Prioritizing reliability over speed
                  -> Message handling is more transactional

Benefits of Data Retention -> This enable real-time data processing
                           -> Consumers can read multiple times and whenever they want
                           -> Replay of message, debugging of historical data

What is Apache Zookeper? (Or Should I say what was Apache Zookeeper)
-> Centralized service for manageing metadata & coordination task for distributed systems
-> External dependency of kafka

---> Cluster Management -> Maintaining a registry of all active broker in the cluster 
---> Leader Election    -> Each kafka partition has a leader broker
                        -> Zookeeper faciliates the election of fthe leader

---> Metadata & Configuration Management 

What is Kafka Raft (KRaft)?
Split-brain Prevention
Quorum (3,5,7 member)
