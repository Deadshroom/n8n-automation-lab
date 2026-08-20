# Order Processing

A multi-workflow n8n example demonstrating webhook-driven processing, input validation, workflow composition, persistence, duplicate detection, and structured responses.

## Overview

This example is composed of a parent workflow and a reusable processing sub-workflow.

The parent workflow acts as the external entry point. It receives an order through an authenticated webhook, validates the request, and delegates processing to the child workflow.

The child workflow handles persistence and processing logic before returning a result to the parent.

## Architecture

`order-webhook-processor.json`

↓ invokes

`process-order-subworkflow.json`

## Parent Workflow — Order Webhook Processor

### `order-webhook-processor.json`

Receives incoming orders through an HTTP webhook.

### Processing Flow

1. Receives a `POST` request through the order webhook.
2. Validates the required fields:

   * `order_id`
   * `customer_id`
   * `total`
3. Returns an HTTP `400` response when required data is missing.
4. Passes valid requests into the Process Order sub-workflow.
5. Returns an HTTP `200` response containing the processing result.

### Concepts Demonstrated

* Webhook triggers
* Header-based authentication
* Request validation
* Conditional branching
* Parent/child workflow orchestration
* Workflow input mapping
* HTTP status codes
* Structured JSON responses

## Child Workflow — Process Order

### `process-order-subworkflow.json`

Receives validated order information from the parent workflow and performs the underlying processing logic.

### Processing Flow

1. Receives:

   * `order_id`
   * `customer_id`
   * `total`

2. Checks the n8n Data Table for an existing order.

3. Evaluates whether the order has already been stored.

4. For a new order:

   * Inserts the order into the Data Table.
   * Records the initial status and receipt timestamp.
   * Calls the external order-processing API.
   * Updates the stored order with the processing result and completion timestamp.

5. For an existing order:

   * Skips duplicate processing.

6. Produces a structured processing result for the parent workflow.

### Concepts Demonstrated

* Reusable sub-workflows
* Explicit workflow inputs
* Data Table queries
* Duplicate detection
* Data persistence
* Record insertion
* Record updates
* External API invocation
* Conditional processing
* Dynamic expressions
* Structured return values

## Files

### `order-webhook-processor.json`

Parent workflow responsible for receiving, validating, and responding to incoming webhook requests.

### `process-order-subworkflow.json`

Child workflow responsible for persistence, duplicate detection, API processing, status updates, and result construction.

## Configuration

These public workflow exports have been sanitized for GitHub.

After importing them into another n8n environment, environment-specific resources must be configured again, including:

* API credentials
* Data Table references
* Parent-to-sub-workflow references
* Assessment or training-specific identifiers

## Training Context

Created while completing the **n8n N8N102 training program** and retained as evidence of hands-on implementation, workflow composition, and experimentation.
