# H4shL4mb

**Automated checksum verification in AWS, powered by Golang, Pulumi, and Lambda.**

## Overview
H4shL4mb is a serverless checksum verification system designed to ensure file integrity in AWS S3. When a file is uploaded to a designated S3 bucket, H4shL4mb automatically calculates its cryptographic hash (MD5, SHA-256, etc.) and logs the results. Pulumi is used for seamless infrastructure as code (IaC) deployment, making the setup and scaling of the service effortless.

## Features
- **Automated Checksum Calculation** – Computes hashes for files uploaded to S3.
- **Multi-Algorithm Support** – Supports MD5, SHA-1, and SHA-256.
- **Serverless & Scalable** – Runs as an AWS Lambda function triggered by S3 events.
- **Pulumi-Powered Deployment** – Infrastructure managed with modern IaC practices.
- **Logging & Monitoring** – Hash results are stored in DynamoDB or logged via CloudWatch.

## Architecture
1. **S3 Bucket Upload** – A file is uploaded to an S3 bucket.
2. **S3 Event Trigger** – The upload triggers an AWS Lambda function.
3. **Checksum Computation** – The Lambda function computes the file’s hash.
4. **Logging & Storage** – Hash results are stored in DynamoDB or CloudWatch.

## Deployment
### Prerequisites
- Pulumi CLI installed
- AWS account with necessary permissions
- Golang installed

### Steps
1. Clone the repository:
   ```sh
   git clone https://github.com/alexi-perkele/H4shL4mb.git
   cd H4shL4mb
   ```
2. Configure AWS credentials:
   ```sh
   export AWS_ACCESS_KEY_ID=your-access-key
   export AWS_SECRET_ACCESS_KEY=your-secret-key
   ```
3. Deploy with Pulumi:
   ```sh
   pulumi up
   ```

## Usage
Once deployed, simply upload a file to the designated S3 bucket. The system will process the file and generate its checksum automatically.

## Roadmap
- Add support for additional checksum algorithms (e.g., BLAKE2, SHA-3).
- Implement an API for hash retrieval and verification.
- Add notifications (SNS, Webhooks) for checksum alerts.

## License
MIT License. See `LICENSE` for details.
