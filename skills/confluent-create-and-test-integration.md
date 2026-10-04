---
name: confluent-create-and-test-integration
description: Create a new notification integration and verify it works by testing the webhook, Slack, or Microsoft Teams endpoint.
api: openapi/confluent-cloud-full.yaml
operations:
- createNotificationsV1Integration
- testNotificationsV1Integration
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/confluent-cloud-full.yaml ; every operationId checked against the contract
---

# confluent-create-and-test-integration

Create a new notification integration and verify it works by testing the webhook, Slack, or Microsoft Teams endpoint.

## Steps

1. 1. Call `createNotificationsV1Integration` with the required request body fields for the integration (e.g., `name`, `type`, `resource`, `resource_type`, and destination‑specific config).
2. 2. Call `testNotificationsV1Integration` with the `integration_id` returned from step 1 and the test payload fields required by the integration type.

## Rules

- Auth: Include one of the supported authentication headers (e.g., `Authorization: Bearer <token>` for `bearerAuth`, `x-api-key: <key>` for `api-key`, etc.).
- Idempotency: The `createNotificationsV1Integration` operation is not guaranteed to be idempotent; avoid duplicate calls or handle duplicate‑resource errors.
- Errors: The API returns standard HTTP error codes (4xx for client errors, 5xx for server errors). Inspect the response body for error details.
