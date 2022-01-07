# KAFKA CLUSTER


https://github.com/bitnami/bitnami-docker-kafka/blob/master/README.md


## create a replicated topic
/opt/bitnami/kafka/bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --topic sales --partitions 3 --replication-factor 3

## Describe topic
/opt/bitnami/kafka/bin/kafka-topics.sh --describe --bootstrap-server localhost:9092 --topic mytopic

## Describe all consumers groups
./kafka-consumer-groups.sh  --bootstrap-server localhost:9092 --describe --all-groups

## listar topicos
./kafka-topics.sh --bootstrap-server localhost:9092 --list
audit
audit_loyalty
audit_smartkargo
fraudCaseCheck
sales


# Kafka Architecture
http://cloudurable.com/blog/kafka-architecture-topics/index.html

## Kafka architecture has 4 actors. These are:
* Broker
* Zookeeper
* Producer(writes data to Kafka.)
* Consumer(reads data from Kafka)

## Zookeeper 
Is open-source software. Kafka uses Zookeeper to manage all Brokers. The data sent is never stored here. Zookeeper’s responsibilities are:
Coordinating brokers.
* Choosing the Leader Partition.
* To ensure that brokers get to know each other.
* Discovering new or deleted Brokers or newly added, changed Topics.

# Partitions
The data in the partition is not stored here forever. Kafka has two storage configurations. 
These are:
* Time-based retention (e.g. 7 days)
* Data size based storage (e.g. 100 GB)