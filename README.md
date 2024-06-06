# CNE430S3bucket
This project demonstrates deploying a static website using Amazon S3 for hosting and Amazon CloudFront for content delivery. It's a great starting point for beginners to get familiar with AWS services.
## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
 - [1. Create a Static Website](#1-create-a-static-website)
 - [2. Set Up an S3 Bucket](#2-set-up-an-s3-bucket)
 - [3. Upload Your Website](#3-upload-your-website)
 - [4. Configure Bucket Policy](#4-configure-bucket-policy)
 - [5. Test Your Website](#5-test-your-website)
 - [6. Set Up CloudFront Distribution](#6-set-up-cloudfront-distribution)
 - [7. Deploy and Test with CloudFront](#7-deploy-and-test-with-cloudfront)
 - [8. (Optional) Use a Custom Domain](#8-optional-use-a-custom-domain)
- [Learning Outcomes](#learning-outcomes)
- [Contributing](#contributing)
- [License](#license)
## Introduction
This project will guide you through the process of deploying a simple static website using Amazon S3 and distributing it globally with Amazon CloudFront. By the end of this tutorial, you will have a fast and secure website accessible from anywhere.
## Prerequisites
- Basic knowledge of HTML, CSS, and JavaScript.
- An AWS account. Sign up for a free tier [here](https://aws.amazon.com/free/).
## Setup Instructions
### 1. Create a Static Website
Create a simple static website using HTML, CSS, and JavaScript. You can use a template from sites like [HTML5 UP](https://html5up.net/) or [Start Bootstrap](https://startbootstrap.com/).
### 2. Set Up an S3 Bucket
1. Log in to the AWS Management Console.
2. Navigate to the S3 service.
3. Create a new S3 bucket. Name it (e.g., `OlaAndAdams-website`) and select a region.
4. Enable "Static website hosting" in the bucket properties and note the endpoint provided.
### 3. Upload Your Website
1. Upload your website files (HTML, CSS, JS) to the S3 bucket.
2. Set permissions to make the bucket public so that everyone can access your website.
### 4. Configure Bucket Policy
Add a bucket policy to allow public read access to your bucket. Here is a sample policy:
```json
{
   "Version": "2012-10-17",
   "Statement": [
       {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::OlaAndAdams-website/*"
       }
   ]
}
5. Test Your Website
Use the S3 bucket endpoint to access your website in the browser and ensure it works correctly.
6. Set Up CloudFront Distribution
Navigate to the CloudFront service.
Create a new CloudFront distribution and set the origin domain to your S3 bucket.
Configure the distribution settings (you can use the default settings for simplicity).
7. Deploy and Test with CloudFront
Once the distribution is created, CloudFront will provide a domain name (e.g., d1234567890.cloudfront.net).
Use this domain to access your website and note the performance improvement.
8. (Optional) Use a Custom Domain
If you have a custom domain, you can configure it with Route 53 and use it with your CloudFront distribution for a professional touch. Refer to the AWS documentation for detailed instructions.
Learning Outcomes
Understand the basics of Amazon S3, including creating buckets, uploading files, and setting permissions.
Learn how to configure static website hosting on S3.
Gain experience with Amazon CloudFront and understand its benefits for content delivery.
Optionally, learn how to integrate Route 53 for DNS management.
Contributing
Contributions are welcome! Please open an issue or submit a pull request if you have any improvements or suggestions.
License
This project is licensed under the MIT License
