
# API Integration Pipeline

An n8n workflow demonstrating API integration, data enrichment, conditional routing, batching, and error-handling patterns.

## Overview

The workflow retrieves order and customer data from separate API endpoints, combines the datasets using a shared customer identifier, and processes the resulting records through several business-rule paths.

The workflow demonstrates how n8n can coordinate multiple API operations and transform the responses into a larger processing pipeline.

## Workflow

1. **Trigger Workflow**

   * Starts through a manual trigger.

2. **Retrieve Orders**

   * Fetches order data from the n8n Academy API.
   * Uses pagination to retrieve multiple pages of results.
   * Retry behavior is enabled.

3. **Retrieve Customers**

   * Fetches customer records in parallel with the order request.
   * Includes a fallback path if customer retrieval encounters an error.

4. **Merge Orders and Customers**

   * Joins order and customer datasets using `customer_id`.
   * Enriches order records with customer information.

5. **Aggregate Orders**

   * Collects enriched order records for submission to the orders queue.

6. **Evaluate Subscription Tier**

   * Separates Enterprise customers from other subscription tiers.

7. **Process Priority Orders**

   * Filters out delivered orders.
   * Processes remaining Enterprise orders in batches.
   * Sends priority orders to the appropriate API endpoint.

8. **Route Non-Enterprise Orders**

   * Routes records according to customer region:

     * North
     * South
     * East
     * West
     * Fallback

9. **Finalize Processing**

   * Sends summary information after priority-order processing completes.

## Concepts Demonstrated

* REST API integration
* HTTP header authentication
* API pagination
* Parallel execution paths
* Dataset merging and enrichment
* Aggregation
* Conditional branching
* Filtering
* Switch-based routing
* Batch processing
* Retry behavior
* Error and fallback paths
* Dynamic n8n expressions
* POST request construction

## Files

### `api-integration-pipeline.json`

Importable n8n workflow containing the complete example.

## Configuration

This public export has been sanitized for GitHub.

Before running the workflow in another n8n environment, configure the required credentials and replace any placeholder assessment or environment-specific values.

## Training Context

Created while completing the **n8n N8N102 training program** and retained as evidence of hands-on workflow implementation and experimentation.
