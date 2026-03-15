# aws-s3-static-website-project
Hosted a static website on amazon aws s3 using static website hosting, bucket policy, and public website endpoint 
# AWS S3 Static Website Hosting

## Project Overview

This project demonstrates how to host a static website using Amazon S3 Static Website Hosting.

The website files are stored inside an S3 bucket and made publicly accessible using bucket policy configuration. The project helps build practical knowledge of AWS storage, public access control, and static website hosting.

---

## Architecture

User  
↓  
Internet  
↓  
Amazon S3 Bucket  
↓  
Static Website Files (`index.html`)

---

## AWS Services Used

- Amazon S3
- S3 Static Website Hosting
- Bucket Policy
- AWS IAM

---

## Configuration Summary

### S3 Bucket
- Bucket Name: `umesh-static-website-project`
- Region: `eu-north-1`

### Object Ownership
- ACLs disabled (Bucket owner enforced)

### Static Website Hosting
- Enabled
- Index document: `index.html`

### Public Access
- Block Public Access disabled for the bucket
- Bucket policy added to allow public read access

---

## Bucket Policy Used

```json
{
  "Version":"2012-10-17",
  "Statement":[
    {
      "Sid":"PublicReadGetObject",
      "Effect":"Allow",
      "Principal":"*",
      "Action":"s3:GetObject",
      "Resource":"arn:aws:s3:::umesh-static-website-project/*"
    }
  ]
}

