# 🌐 Static Website Hosting with AWS S3

![AWS](https://img.shields.io/badge/AWS-S3-orange?logo=amazon-aws)
![Website](https://img.shields.io/badge/Hosting-Static%20Website-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📋 Project Overview

This project demonstrates how to host a static website (HTML, CSS, JavaScript) using **Amazon S3 (Simple Storage Service)**. AWS S3 provides a simple, scalable, and cost-effective way to serve static content directly over the web without requiring a server.

---

## 🧰 Tech Stack

- **Cloud Service**: Amazon S3
- **Website Stack**: HTML, CSS, JS (Static Assets)
- **Optional**: Route 53 (Custom Domain), CloudFront (CDN), SSL (HTTPS)

---

## 🚀 Setup Instructions

### Step 1: Create an S3 Bucket

- Go to the [AWS S3 Console](https://s3.console.aws.amazon.com/s3/).
- Click **"Create Bucket"**.
- Name your bucket (must be globally unique).
- **Uncheck** "Block all public access".
- Enable versioning (optional).

### Step 2: Upload Website Files

- Upload your `index.html`, `style.css`, etc. into the bucket.
- Use the **Upload** button or drag-and-drop.

### Step 3: Enable Static Website Hosting

- Go to **Bucket → Properties**.
- Scroll to **Static website hosting** section.
- Enable it, set:
  - **Index document**: `index.html`
- Save changes.

### Step 4: Make Files Public

Go to **Permissions** → **Bucket Policy**, add this:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}


✅ Access the Website
Use the S3 endpoint provided in the Static Website Hosting section:

http://demo-pet-shop-website.s3-website.ap-south-1.amazonaws.com/

🔐 Optional Enhancements
HTTPS: Use AWS CloudFront with S3 to enable HTTPS
Domain Name: Map a custom domain using AWS Route 53
SSL: Use ACM for free SSL certificate
Logging: Enable access logs to track visits

📈 Learning Outcomes
Set up a static website on AWS S3
Configure S3 permissions and policies
Understand hosting architecture without servers
Learn optional CDN and domain mapping techniques

🤝 Contributing
Pull requests and suggestions are welcome. Please fork the repo and submit a PR.

📄 License
This project is open-source and free to use for educational purposes.
