---
name: confluent-create-and-validate-integration
description: Create a new Integration, validate its configuration, and retrieve the created Integration details.
api: openapi/confluent-cloud-full.yaml
operations:
- createPimV2Integration
- validatePimV2Integration
- getPimV2Integration
generated: '2026-10-04'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/confluent-cloud-full.yaml ; every operationId checked against the contract
---

# confluent-create-and-validate-integration

Create a new Integration, validate its configuration, and retrieve the created Integration details.

## Steps

1. 1. Call `createPimV2Integration` with the Integration definition in the request body and include an `Authorization` header using one of the supported auth schemes.
2. 2. Call `validatePimV2Integration` with the same Integration definition in the request body and include an `Authorization` header.
3. 3. Call `getPimV2Integration` with the `{id}` path parameter returned from the create step and include an `Authorization` header.

## Rules

- Authentication: All requests must include an `Authorization` header (api-key, bearer token, basic auth, etc.) as defined in the provider's auth schemes.
- Idempotency: The `createPimV2Integration` operation is not idempotent; repeat calls will create duplicate resources unless the client supplies a unique identifier.
- Errors: The API returns standard HTTP error codes (e.g., 400 for validation errors, 401/403 for authentication failures, 404 for missing Integration, 5xx for server errors).
