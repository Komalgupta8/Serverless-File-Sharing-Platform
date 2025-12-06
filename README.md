# Step-by-Step Guide to Build Serverless File Sharing Platform

## 📌 Project Description

The Serverless File Sharing Platform enables users to securely upload and download files through a simple HTTP interface. It uses:

- **AWS Lambda** for fully managed compute
- **Amazon API Gateway** for routing requests
- **Amazon S3** for scalable and durable file storage

This project is ideal for file distribution, collaboration, and lightweight document storage — with zero server maintenance.

---

## 📌 Use Cases

- Upload and share files securely without servers
- Distribute downloadable content (documents, images, media)
- Enable remote team members to exchange files efficiently

---

## 🏗️ Architecture Overview


### Visual Architecture


![Architecture Diagram](https://github.com/yeshwanthlm/Serverless-File-Sharing-Platform/assets/66474973/702f29d8-8eca-4d17-9842-e291ff945801)

---

## 🧰 Prerequisites

✔ AWS Account  
✔ Permission to create:  
&nbsp;&nbsp;&nbsp;&nbsp;• Lambda Functions  
&nbsp;&nbsp;&nbsp;&nbsp;• API Gateway  
&nbsp;&nbsp;&nbsp;&nbsp;• S3 Buckets  
✔ Basic understanding of HTTP requests

---

## 🚀 Deployment Steps

### 1️⃣ Create S3 Bucket
Create a bucket for storing uploaded files. Example:


---

### 2️⃣ Create Upload Lambda (UploadFunction)
Handles POST requests and stores the request body as a file in S3.  
Ensure the execution role has S3 **write** permission.

---

### 3️⃣ Create Download Lambda (DownloadFunction)
Handles GET requests and provides secure access to files stored in S3.  
Ensure the execution role has S3 **read** permission.

---

### 4️⃣ Configure API Gateway

- Create a REST API
- Resource: `/files`
- Methods:
  - **POST** → UploadFunction
  - **GET** → DownloadFunction
- Enable **Lambda Proxy Integration** for both

---

### 5️⃣ Deploy API

- Choose: **Actions → Deploy API**
- Stage: `dev`
- Copy and save the endpoint URL for testing

---

## 🧪 Testing the Platform

### Upload a File
Send a POST request with raw text body:


Example tools: Postman / CURL

---

### Download a File
Send a GET request:


Verify the file downloads correctly.

---

