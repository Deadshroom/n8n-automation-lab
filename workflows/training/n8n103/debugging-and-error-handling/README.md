# Debugging and Error Handling

A multi-workflow n8n example demonstrating retry behavior, intentional failure testing, and centralized error handling.

## Architecture

`debugging-practice.json`

↓ calls

`failure-test.json`

↓ intentionally fails and invokes

`error-handler.json`

## Debugging Practice

Calls an unreliable Academy endpoint with retry behavior enabled, submits the successful retry result, and then calls the separate failure-test webhook.

### Concepts
- Retry-on-failure configuration
- Maximum retry attempts
- Chained HTTP requests
- Failure-testing orchestration

## Failure Test

Exposes an authenticated webhook and deliberately calls an endpoint designed to fail. The workflow is configured to use the dedicated error workflow when the production execution fails.

### Concepts
- Webhook triggers
- Intentional failure testing
- Production error-workflow configuration
- Error propagation

## Error Handler

Uses n8n's Error Trigger to receive failure metadata and submit diagnostic information including workflow name, workflow ID, execution URL, error message, and the last executed node.

### Concepts
- Error Trigger
- Centralized error handling
- Failure metadata
- Operational diagnostics
- Error-report API integration

## Files

- `debugging-practice.json`
- `failure-test.json`
- `error-handler.json`

## Configuration

The public exports remove credential and webhook IDs, replace assessment identifiers, replace the personal n8n hostname with `YOUR_N8N_HOST`, and replace the linked error-workflow ID with `REPLACE_WITH_ERROR_WORKFLOW_ID`.

The relationship between `failure-test.json` and `error-handler.json` must be reconfigured after import.

## Training Context

Created as part of the N8N103 training material represented in this repository.
