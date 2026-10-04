---
name: confluent-create-subscription
description: Create a new notification subscription and retrieve its details.
api: openapi/confluent-cloud-full.yaml
operations:
- createNotificationsV1Subscription
- getNotificationsV1Subscription
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/confluent-cloud-full.yaml ; every operationId checked against the contract
---

# confluent-create-subscription

Create a new notification subscription and retrieve its details.

## Steps

1. 1. Call `createNotificationsV1Subscription` with the request body containing the subscription fields (e.g., `name`, `topic_name`, `delivery_method`).
2. 2. Call `getNotificationsV1Subscription` with the path parameter `id` returned from the create call to read the subscription.

## Rules

- Authentication: include one of the supported auth schemes (e.g., `api-key`, `bearerAuth`, `cloud-api-key`, etc.) in the request headers.
- The `createNotificationsV1Subscription` operation may be retried safely if it returns a 409 conflict, indicating the subscription already exists.
