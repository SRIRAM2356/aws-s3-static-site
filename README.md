# AWS S3 Static Website Hosting 🚀

This is a simple project that demonstrates how to host a **static website** using **Amazon S3**.  
It contains an `index.html` homepage and an optional `error.html` page.

---

## 📌 Project Overview
- **Service Used:** Amazon S3 (Simple Storage Service)  
- **Objective:** Host a static website on AWS  
- **Files:**  
  - `index.html` → Home page  
  - `error.html` → Custom error page (404, etc.)

---

## ⚡ Steps to Deploy

### 1. Create an S3 Bucket
- Go to AWS Console → S3 → Create Bucket  
- Give it a unique name (example: `my-first-aws-site`)  
- Disable **Block all public access**  

### 2. Upload Website Files
- Upload `index.html` (and `error.html`) under the **Objects tab**  

### 3. Configure Static Website Hosting
- Go to **Properties → Static Website Hosting**  
- Set:
  - Index document → `index.html`  
  - Error document → `error.html`  

### 4. Add Bucket Policy
Add this JSON under **Permissions → Bucket Policy** (replace with your bucket name):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-first-aws-site/*"
    }
  ]
}

