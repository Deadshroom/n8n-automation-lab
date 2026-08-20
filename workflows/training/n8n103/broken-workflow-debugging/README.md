# Broken Workflow Debugging

An n8n debugging exercise based on repairing an intentionally broken workflow.

The workflow retrieves order and customer data, supplies fallback customer data when necessary, merges the datasets, aggregates the enriched orders, and submits the result for validation.

## Issues Documented in the Exercise

The workflow's own training notes identify three repaired problems:

1. Missing authentication and assessment-header configuration on the order request.
2. An incorrect merge field (`customerId` instead of `customer_id`).
3. A downstream reference to a deleted `AggregateOrders` node.

## Concepts Demonstrated

- Workflow troubleshooting
- HTTP authentication repair
- Data-key mismatch diagnosis
- Merge configuration
- Broken node-reference diagnosis
- Error-output routing
- Fallback data
- Aggregation
- Validation through an API endpoint

## File

`broken-workflow-debugging.json`

## Configuration

The public export removes credential IDs and replaces the training assessment identifier with `YOUR_ASSESSMENT_ID`.

## Training Context

Created as part of the N8N103 debugging material represented in this repository.
