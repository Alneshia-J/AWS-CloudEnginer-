# AWS Deployment Screenshots

## Overview
This page documents the step-by-step deployment of The Unknown restaurant website to AWS using Amazon S3 Static Website Hosting.

## Deployment Steps & Screenshots

### Step 1: Create an S3 Bucket
![Create S3 Bucket](../images/deploy-01-create-bucket.png)

- Go to AWS Console → S3
- Click "Create bucket"
- Bucket name: the-unknown-restaurant
- Region: af-south-1 (Africa - Cape Town)
- Uncheck "Block all public access"
- Click "Create bucket"

### Step 2: Enable Static Website Hosting
![Enable Static Hosting](../images/deploy-02-static-hosting.png)

- Open your bucket → Properties tab
- Scroll to "Static website hosting"
- Click "Edit"
- Select "Enable"
- Index document: index.html
- Click "Save changes"

### Step 3: Upload Website Files
![Upload Files](../images/deploy-03-upload-files.png)

- Open your bucket → Objects tab
- Click "Upload"
- Drag and drop all project files:
  - index.html
  - booking.html
  - order.html
  - confirmation.html
  - css/ folder
  - js/ folder
  - images/ folder
- Click "Upload"

### Step 4: Set Bucket Policy (Make Public)
![Bucket Policy](../images/deploy-04-bucket-policy.png)

- Open your bucket → Permissions tab
- Scroll to "Bucket policy"
- Click "Edit"
- Paste the following policy:

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::the-unknown-restaurant/*"
        }
    ]
}

- Click "Save changes"

### Step 5: Access Your Live Website
![Live Website](../images/deploy-05-live-website.png)

- Go to Properties → Static website hosting
- Copy the "Bucket website endpoint" URL
- Open the URL in your browser
- Your website is now LIVE!

## Website URL
- Endpoint: http://the-unknown-restaurant.s3-website.af-south-1.amazonaws.com

## Deployment Checklist
- [ ] S3 bucket created
- [ ] Static website hosting enabled
- [ ] All files uploaded
- [ ] Bucket policy set to public
- [ ] Website accessible via endpoint URL
- [ ] All pages load correctly
- [ ] Navigation links work between pages
- [ ] Forms display properly
