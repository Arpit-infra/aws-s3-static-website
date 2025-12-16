# AWS S3 Static Website Hosting

## Overview
This project demonstrates hosting a **static website on Amazon S3** using
IAM permissions and bucket policies.

The website includes:
- A main `index.html` page
- A custom `error.html` page for error handling

The goal is to understand **S3 static hosting, public access control, and IAM-based permissions**
using AWS Console and AWS CLI concepts.


## Architecture
User → S3 Static Website Endpoint → HTML Files

This is a **serverless** setup with no EC2 or backend services.


## AWS Services Used
- Amazon S3
- IAM
- S3 Bucket Policy
- AWS CLI (conceptual understanding)


## Project Structure
aws-s3-static-website/
├── site/
│ ├── index.html
│ └── error.html
└── screenshots/
├── s3-objects.png
├── bucket-policy.png
├── website-index.png
└── website-error.png



## Configuration Steps

### 1. S3 Bucket Setup
- Created an S3 bucket
- Disabled **Block Public Access**
- Enabled **Static Website Hosting**
  - Index document: `index.html`
  - Error document: `error.html`

---

### 2. Bucket Policy
A public read bucket policy was applied to allow access to website files:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::aws-arpit-static-website/*"
    }
  ]
}


