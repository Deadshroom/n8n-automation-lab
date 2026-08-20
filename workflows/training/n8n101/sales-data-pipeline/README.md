# Sales Data Pipeline

An n8n workflow that retrieves sales data and transforms it into multiple downstream outputs for order processing, regional analysis, and report generation.

## Processing Flow

1. Retrieve sales data from the Academy API.
2. Split the returned `orders` collection into individual items.
3. Calculate `order_total` from quantity and unit price.
4. Send an aggregated order collection to the order-processing endpoint.
5. Filter delivered orders from non-delivered orders.
6. Summarize delivered orders by region using total, count, and average order value.
7. Rename generated summary fields into report-friendly names.
8. Aggregate regional summaries and submit the analysis.
9. Add report metadata, convert the result to CSV, and submit the generated report.

## Concepts Demonstrated

- REST API integration
- Header authentication
- Data splitting
- Field transformation
- Calculated fields
- Aggregation
- Conditional branching
- Regional grouping and summarization
- Field renaming
- CSV generation
- Multiple downstream API submissions
- Debugging data-quality issues

## File

`sales-data-pipeline.json`

## Configuration

The public export removes credential IDs and replaces training-specific assessment identifiers with `YOUR_ASSESSMENT_ID`.

## Training Context

Created as part of the n8n Foundations/N8N101 training exercises represented in this repository.
