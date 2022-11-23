---
title: Kafka
weight: 11
---

## Read messages from Kafka

### Number of partitions and their message count 

Substitute `dataset-events` with the desired topic.

```bash
kubectl exec -it kafka-1-0 -- /bin/kafka-run-class kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic dataset-events
```

#### Example output

```txt
dataset-events:0:47472
dataset-events:1:49949
dataset-events:2:49361
dataset-events:3:50122
```

### Read last n messages from partition in topic

Substitute _topic_, _partition_ and _offset_ parameters based on output from command above.
Remember that all messages with the same key (often some sort of ID) is put on the same partition.

```bash
kubectl exec -it schema-registry-1-0 -- kafka-avro-console-consumer --bootstrap-server kafka-1:9092 --property schema.registry.url=http://localhost:8081 --topic dataset-events --partition 0 --offset 47470
```

You may redirect the command output to a file and then use `jq` to get a more readable output.

```bash
# Pipe output into file 'kafka-output' while also seeing output in terminal
kubectl exec ... | tee kafka-output

# Show whole messages
cat kafka-output | grep "{" | jq

# Show selected fields in messages
cat kafka-output | grep "{" | jq "{type,fdkId,timestamp}"
```
