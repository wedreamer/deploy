# kafka

## demo kafka

## Persisting your data

```bash
# Create a topic
docker exec kafka /opt/bitnami/kafka/bin/kafka-topics.sh --bootstrap-server kafka:9092 --create --topic quickstart
# Write messages to the topic
docker exec --interactive --tty kafka /opt/bitnami/kafka/bin/kafka-console-producer.sh --bootstrap-server kafka:9092 --topic quickstart
# Read messages from the topic
docker exec --interactive --tty kafka /opt/bitnami/kafka/bin/kafka-console-consumer.sh --bootstrap-server kafka:9092 --topic quickstart --from-beginning
# Write some more messages
docker exec --interactive --tty kafka /opt/bitnami/kafka/bin/kafka-console-producer.sh --bootstrap-server kafka:9092 --topic quickstart
```

## Accessing Apache Kafka with internal and external clients

```bash
# Producer and consumer using external client
kafka-console-producer.sh --producer.config /opt/bitnami/kafka/config/producer.properties --bootstrap-server 172.24.20.93:9094 --topic test
kafka-console-consumer.sh --consumer.config /opt/bitnami/kafka/config/consumer.properties --bootstrap-server 172.24.20.93:9094 --topic test --from-beginning

# Producer and consumer using internal client
kafka-console-producer.sh --producer.config /opt/bitnami/kafka/config/producer.properties --bootstrap-server kafka:9092 --topic test
kafka-console-consumer.sh --consumer.config /opt/bitnami/kafka/config/consumer.properties --bootstrap-server kafka:9092 --topic test --from-beginning
```