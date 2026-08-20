# n8n Automation Lab

A collection of hands-on n8n workflows focused on workflow automation, API integration, orchestration, data processing, and AI-enabled automation.

This repository serves as a working lab for documenting practical experience with n8n through structured training, experimentation, and original workflow development.

## Repository Structure

```text
n8n-automation-lab/
├── README.md
└── workflows/
    └── training/
        └── n8n102/
            ├── api-integration-pipeline/
            │   ├── README.md
            │   └── api-integration-pipeline.json
            │
            └── order-processing/
                ├── README.md
                ├── order-webhook-processor.json
                └── process-order-subworkflow.json
```

Each folder represents a logical automation example rather than an individual workflow file.

Some examples may contain a single workflow, while others may contain multiple workflows that operate together as part of a larger solution.

## Current Examples

### API Integration Pipeline

An API-driven processing pipeline that retrieves order and customer data, enriches records, and routes them through different processing paths.

Concepts demonstrated include:

* REST API integration
* HTTP authentication
* Pagination
* Parallel execution
* Data merging and enrichment
* Aggregation
* Conditional branching
* Filtering
* Regional routing
* Batch processing
* Retry and fallback behavior

The workflow retrieves orders and customers independently, joins them using `customer_id`, evaluates subscription tiers, and processes records through multiple downstream paths.

**Location:**
`workflows/training/n8n102/api-integration-pipeline/`

---

### Order Processing

A multi-workflow example demonstrating webhook-driven order processing and reusable workflow composition.

The solution consists of:

* A parent webhook workflow responsible for receiving and validating requests
* A reusable sub-workflow responsible for persistence and processing logic

Concepts demonstrated include:

* Webhook triggers
* Request validation
* Parent/child workflow orchestration
* Workflow inputs
* Data Table operations
* Duplicate detection
* Data persistence
* External API calls
* Record updates
* Structured HTTP responses
* Conditional processing

The parent workflow receives `order_id`, `customer_id`, and `total`, validates the incoming request, and delegates processing to the child workflow. The child workflow checks for existing orders, stores new records, invokes the processing API, updates processing status, and returns the result.

**Location:**
`workflows/training/n8n102/order-processing/`

## Repository Organization

Workflows are organized by **use case or logical solution**, not simply by individual workflow files.

The general pattern is:

```text
example-name/
├── README.md
├── primary-workflow.json
├── supporting-workflow.json
└── ...
```

This allows related parent workflows, sub-workflows, documentation, screenshots, sample payloads, and supporting resources to remain grouped together.

## Training Workflows

The current examples were created while completing the **n8n N8N102 training program**.

They are retained here as evidence of hands-on implementation and may be modified, expanded, or used as the foundation for additional experiments.

Training-derived work is identified as such rather than presented as original project requirements.

## Public Workflow Exports

Workflow exports in this repository are sanitized before publication.

Environment-specific or sensitive values may be removed or replaced with placeholders, including:

* Credential IDs
* API keys and tokens
* Assessment identifiers
* Webhook instance IDs
* Internal workflow IDs
* Data Table IDs
* Project-specific resource paths
* Execution or pinned test data

Because of this, imported workflows may require configuration before they can be executed in another n8n environment.

## Areas of Exploration

This repository will continue to expand into areas including:

* API orchestration
* Webhook-driven automation
* Workflow composition
* Data transformation
* Error handling and resiliency
* External service integrations
* AI agents
* LLM integrations
* Tool-enabled agents
* Agentic workflows
* Human-in-the-loop automation
* Event-driven automation
* Reusable automation patterns

## Purpose

The purpose of this repository is simple:

**Build things, document them, and preserve the implementation as evidence of hands-on experience.**
