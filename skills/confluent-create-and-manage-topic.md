---
name: confluent-create-and-manage-topic
description: Create a new Kafka topic, verify its creation, optionally update its partition count, and then delete it.
api: openapi/confluent-cloud-full.yaml
operations:
- createKafkaTopic
- getKafkaTopic
- updatePartitionCountKafkaTopic
- deleteKafkaTopic
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/confluent-cloud-full.yaml ; every operationId checked against the contract
---

# confluent-create-and-manage-topic

Create a new Kafka topic, verify its creation, optionally update its partition count, and then delete it.

## Steps

1. 1. Use `createKafkaTopic` with required body fields `topic_name`, `partitions_count`, and optional `configs`.
2. 2. Use `getKafkaTopic` with path parameters `cluster_id` and `topic_name` to retrieve the created topic.
3. 3. (Optional) Use `updatePartitionCountKafkaTopic` with path parameters `cluster_id`, `topic_name` and body field `partitions_count` to change partition count.
4. 4. Use `deleteKafkaTopic` with path parameters `cluster_id` and `topic_name` to remove the topic.

## Rules

- Auth: Include an appropriate authentication header such as `Authorization: Bearer <token>` using one of the supported schemes (api-key, bearerAuth, etc.).
- Idempotency: `createKafkaTopic` is not idempotent; repeat calls may return a conflict if the topic already exists.
- Errors: Expect HTTP 4xx for invalid parameters or authentication failures, and HTTP 5xx for server errors.
