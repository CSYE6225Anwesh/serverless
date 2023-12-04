# Serverless Submission Processor

This Lambda function processes submissions received through SNS events, downloads files from a provided URL, uploads them to Google Cloud Storage (GCS), notifies the user via email using Mailgun, and logs the event to AWS DynamoDB.

## Features

- File download from a URL
- File upload to GCS
- Email notifications via Mailgun
- Logging to DynamoDB

## Prerequisites

- Node.js installed
- AWS CLI configured with Lambda and DynamoDB access
- Google Cloud account with a configured GCS bucket
- Mailgun account with API key and domain

## Environment Variables

Set the following environment variables in your Lambda function:

- `GCS_SERVICE_ACCOUNT_KEY`: Base64 encoded Google Cloud service account key
- `GOOGLE_CLIENT_MAIL`: Google Cloud service account email
- `GOOGLE_PROJECT_ID`: Google Cloud project ID
- `GCS_BUCKET_NAME`: Google Cloud Storage bucket name
- `MAILGUN_API_KEY`: Mailgun API key
- `MAILGUN_DOMAIN`: Mailgun domain
- `DYNAMODB_TABLE_NAME`: AWS DynamoDB table name

## Deployment

To deploy this function:

1. Zip the function files including `node_modules`.
2. Upload the zip file to AWS Lambda.
3. Set the environment variables in the Lambda configuration.

## Usage

Trigger the Lambda function by sending an SNS event with the expected message structure. The function will process the event and perform the necessary actions.
