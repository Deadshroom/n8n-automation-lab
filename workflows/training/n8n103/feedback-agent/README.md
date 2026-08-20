# Feedback Agent

A tool-enabled AI customer-service agent built in n8n.

The agent receives conversational input through a Chat Trigger and can call external HTTP tools when it needs order, customer, or product information.

## Tools

- **Order Status** — retrieves order or delivery status using `order_id`
- **Customer Info** — retrieves account and subscription information using `customer_id`
- **Product Info** — retrieves product details using `product_name`

The tool parameters are populated dynamically from the model using n8n's `$fromAI()` expressions.

## Concepts Demonstrated

- Chat-triggered workflows
- AI Agent node
- LLM integration through Groq
- Tool-enabled agent execution
- HTTP Request Tool nodes
- Model-driven parameter extraction
- System prompting
- API authentication
- Multi-tool orchestration

## File

`feedback-agent.json`

## Configuration

The public export removes the chat webhook ID, Groq credential ID, n8n Academy credential IDs, and replaces the training assessment identifier with `YOUR_ASSESSMENT_ID`.

After import, reconnect the Groq and Academy credentials.

## Training Context

Created as part of the N8N103 training material represented in this repository.
