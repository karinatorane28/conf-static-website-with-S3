Configure Static Website with S3
This project provides a step-by-step guide to configuring a static website using Amazon S3 (Simple Storage Service). You can host your static assets like HTML, CSS, and JavaScript files effortlessly, making it a great choice for personal projects, portfolios, and documentation.

Table of Contents
Prerequisites
Installation
Configuration
Deployment
Accessing Your Website
License
Prerequisites
Before you begin, ensure you have the following:

An AWS account
AWS CLI installed and configured (optional, but recommended)
Basic knowledge of AWS services
Installation
Clone the Repository:

bash
Copy code
git clone https://github.com/yourusername/configure-static-website-with-S3.git
cd configure-static-website-with-S3
Navigate to your project directory:

Make sure to place your static files (HTML, CSS, JS) in the designated folder, e.g., public/.

Configuration
Create an S3 Bucket:

Go to the AWS Management Console.
Navigate to S3 and click on "Create Bucket."
Choose a unique bucket name and select the region.
Disable "Block all public access" to allow public access to your website files.
Configure Bucket for Static Website Hosting:

Select your newly created bucket.
Go to the "Properties" tab.
Enable "Static website hosting."
Specify your index document (e.g., index.html) and an optional error document (e.g., 404.html).
Set Bucket Policy:

To make your website publicly accessible, add the following bucket policy:
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
Replace your-bucket-name with the name of your bucket.

Deployment
Upload Your Files:

You can upload files via the AWS Management Console or use the AWS CLI:
aws s3 sync public/ s3://your-bucket-name

Verify Upload:

Check your S3 bucket to ensure all files are uploaded successfully.

Accessing Your Website
Once your website is configured and your files are uploaded, you can access it via:
http://your-bucket-name.s3-website-your-region.amazonaws.com

