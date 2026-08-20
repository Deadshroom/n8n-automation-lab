# n8n N8N102 Training

This directory contains workflow implementations created while completing the **n8n N8N102 training program**.

N8N102 builds on the fundamentals of workflow creation by introducing more involved automation patterns in which multiple nodes, APIs, data sources, decision paths, and workflows work together as part of a larger process.

## Focus of the Training

The exercises represented in this repository explore concepts such as:

* REST API integration
* HTTP requests and responses
* API authentication
* Pagination
* Webhook-driven workflows
* Input validation
* Data transformation and enrichment
* Merging data from multiple sources
* Conditional logic
* Filtering and routing
* Batch processing
* Error and fallback handling
* n8n Data Tables
* Workflow-to-workflow execution
* Reusable sub-workflows
* Data persistence
* Dynamic expressions
* Structured workflow inputs and outputs

Rather than treating each node as an isolated task, these exercises demonstrate how n8n can be used to coordinate multiple operations into larger automation pipelines.

## Training Examples

### API Integration Pipeline

Demonstrates a multi-stage API processing workflow that retrieves orders and customer records, combines the datasets, applies business rules, and routes records through different processing paths.

`api-integration-pipeline/`

### Order Processing

Demonstrates an event-driven order-processing architecture composed of an authenticated webhook workflow and a reusable processing sub-workflow.

The example includes request validation, duplicate detection, persistence, external API processing, status updates, and structured responses.

`order-processing/`

## Repository Approach

The original training exercises are preserved here as **hands-on implementation evidence** rather than simply as course completion records.

Workflow exports may be reorganized, renamed, documented, and sanitized for public publication while preserving the underlying implementation.

Each logical exercise is stored in its own directory so related workflows and supporting documentation remain together.

## Note on Configuration

Public workflow exports are sanitized before being committed to GitHub.

Credentials, account-specific identifiers, resource IDs, execution data, and other environment-specific values may therefore be removed or replaced with placeholders.

Imported workflows may require configuration before they can be executed in another n8n environment.
