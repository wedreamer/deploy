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

