# Feedback Pipeline

An AI-assisted n8n pipeline that retrieves customer feedback, classifies it into structured categories, and generates a response informed by that classification.

## Processing Flow

1. Retrieve feedback from the Academy API.
2. Select an item for processing.
3. Classify the feedback with an LLM.
4. Parse the model output into a structured schema:
   - sentiment
   - topic
   - urgency
   - key issue
5. Combine the classification with the original feedback data.
6. Generate a short customer-service response using the classification as context.
7. Submit the generated response to the Academy endpoint.

## Concepts Demonstrated

- LLM chains
- Multiple model nodes
- Structured output parsing
- Prompt design
- Sentiment/topic/urgency classification
- Data mapping between AI and standard workflow nodes
- Retry behavior
- API integration
- AI-generated response construction

## File

`feedback-pipeline.json`

## Configuration

The public export removes Groq and Academy credential IDs and replaces training-specific assessment identifiers with `YOUR_ASSESSMENT_ID`.

Reconnect the required credentials after import.

## Training Context

Created as part of the N8N103 training material represented in this repository.
