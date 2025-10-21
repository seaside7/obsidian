# Halodesk Configuration

## AWS Configuration
- AWS credentials have been removed for security
- Use environment variables or AWS CLI configuration instead

## WhatsApp Configuration
- WhatsApp AppId and secrets have been removed for security
- Store these in secure environment variables

## Google Drive Configuration
- Google Drive client ID has been removed for security
- Store these in secure environment variables

## System User
- System user credentials have been removed for security

## AWS S3 Commands
```bash
aws s3 cp halodesk s3://halodesk/ --recursive
```
