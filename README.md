# Kafka

# With Zookeeper

1. Start Zookeeper
~/kafka_2.13-3.9.0/bin/zookeeper-server-start.sh ~/kafka_2.13-3.9.0/config/zookeeper.properties

2. Start Kafka
kafka-server-start.sh ~/kafka_2.13-3.9.0/config/server.properties

# KRaft (better)

1. Generate UUID
kafka-storage.sh random-uuid

2. Insert here
kafka-storage.sh format -t <uuid> -c ~/kafka_2.13-3.9.0/config/kraft/server.properties

3. Start server
kafka-server-start.sh ~/kafka_2.13-3.9.0/config/kraft/server.properties

# Basic Operations (localhost)

1. Create
kafka-topics.sh --bootstrap-server localhost:9092 --topic first_topic --create

2. Create with deets
kafka-topics.sh --bootstrap-server localhost:9092 --topic second_topic --create --partitions 3 --replication-factor 1

3. Delete
kafka-topics.sh --bootstrap-server localhost:9092 --topic topic_name --delete

4. Describe
kafka-topics.sh --bootstrap-server localhost:9092 --topic second_topic --describe

5. List
kafka-topics.sh --bootstrap-server localhost:9092 --list

# Producing
1. Basic
kafka-console-producer.sh --bootstrap-server localhost:9092 --topic first_topic

2. Producing with acks
kafka-console-producer.sh --bootstrap-server localhost:9092 --topic first_topic --producer-property acks=all

3. Producting with keys
kafka-console-producer.sh --bootstrap-server localhost:9092 --topic first_topic --property parse.key=true --property key.separator=:
>example key:example value
>name:Stephane



