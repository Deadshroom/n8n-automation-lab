# n8n N8N103 Training

This directory contains hands-on workflow implementations associated with the N8N103 training material represented in this repository.

The examples preserved here focus on AI-enabled automation, tool-enabled agents, structured LLM output, retry behavior, debugging, failure handling, and reusable operational error workflows.

## Examples

### Feedback Agent
A chat-triggered AI customer-service agent with HTTP tools for order, customer, and product lookups.

`feedback-agent/`

### Feedback Pipeline
An AI-assisted workflow that classifies customer feedback using structured output and generates a classification-aware response.

`feedback-pipeline/`

### Debugging and Error Handling
A multi-workflow example that tests retries, intentionally triggers a production failure, and routes failure metadata into a dedicated error workflow.

`debugging-and-error-handling/`

### Broken Workflow Debugging
A repair exercise demonstrating diagnosis and correction of configuration, merge-field, and node-reference problems.

`broken-workflow-debugging/`

## Public Export Note

Environment-specific identifiers, credential IDs, webhook IDs, and user-hosted URLs are sanitized before publication. Imported workflows may require reconfiguration before execution.
