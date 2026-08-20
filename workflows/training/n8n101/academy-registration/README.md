# Academy Registration

A small n8n training workflow demonstrating a manual trigger and an authenticated HTTP request to the n8n Academy registration endpoint.

## Flow

1. Start the workflow manually.
2. Submit registration metadata to the Academy API.
3. Pass the assessment identifier, workflow name, and training tag as query parameters.

## Concepts Demonstrated

- Manual workflow triggers
- HTTP Request node configuration
- Header-based credentials
- Query parameters
- API integration

## File

`academy-registration.json`

## Configuration

The public export replaces the original assessment identifier and removes the exported credential ID. Configure the required n8n Academy credential and replace `YOUR_ASSESSMENT_ID` before execution.

## Training Context

Created as part of the N8N101 training material.
