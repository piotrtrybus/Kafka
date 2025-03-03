# Kafka

# with Zookeeper

1. Start Zookeeper
~/kafka_2.13-3.0.0/bin/zookeeper-server-start.sh ~/kafka_2.13-3.9.0/config/zookeeper.properties

2. Start Kafka
kafka-server-start.sh

# KRaft (better)

1. Generate UUID
kafka-storage.sh random-uuid

2. Insert here
kafka-storage.sh format -t <uuid> -c ~/kafka_2.13-3.9.0/config/kraft/server.properties

3. Start server
kafka-server-start.sh ~/kafka_2.13-3.9.0/config/kraft/server.properties

