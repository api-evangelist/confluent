---
name: confluent-connectors-create-and-manage
description: Create a new connector, view and update its configuration, then optionally delete it.
api: openapi/confluent-cloud-full.yaml
operations:
- createConnectv1Connector
- getConnectv1ConnectorConfig
- createOrUpdateConnectv1ConnectorConfig
- readConnectv1Connector
- deleteConnectv1Connector
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/confluent-cloud-full.yaml ; every operationId checked against the contract
---

# confluent-connectors-create-and-manage

Create a new connector, view and update its configuration, then optionally delete it.

## Steps

1. 1. Call `createConnectv1Connector` with path parameters `environment_id`, `kafka_cluster_id` and request body containing the connector definition.
2. 2. Call `getConnectv1ConnectorConfig` with path parameters `environment_id`, `kafka_cluster_id`, `connector_name` to read the current configuration.
3. 3. Call `createOrUpdateConnectv1ConnectorConfig` with path parameters `environment_id`, `kafka_cluster_id`, `connector_name` and a request body containing the updated configuration.
4. 4. Call `readConnectv1Connector` with path parameters `environment_id`, `kafka_cluster_id`, `connector_name` to retrieve the connector details.
5. 5. (Optional) Call `deleteConnectv1Connector` with path parameters `environment_id`, `kafka_cluster_id`, `connector_name` to remove the connector.

## Rules

- All requests require an authentication header using one of the supported schemes (e.g., `Authorization: Bearer <token>` or `x-api-key: <key>`).
- The `createConnectv1Connector` operation is not idempotent; repeat calls will create duplicate connectors unless the connector name is unique.
