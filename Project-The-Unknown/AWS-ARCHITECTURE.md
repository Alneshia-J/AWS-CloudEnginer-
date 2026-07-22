# AWS Architecture

## Overview
The Unknown restaurant website is built using a serverless architecture on AWS. This approach eliminates the need for traditional servers, reduces costs, and provides automatic scaling.

## AWS Services Used

### Amazon S3 (Simple Storage Service)
- Purpose: Hosts the static website (HTML, CSS, JavaScript, images)
- Why: 99.999999999% durability, auto-scaling, low cost
- Status: Implemented (Phase 1 Complete)

### AWS Cognito
- Purpose: Manages user authentication and customer accounts
- Why: Secure login, customer booking history, personalised experience
- Status: Future Phase

### Amazon DynamoDB
- Purpose: Stores customer profiles, bookings, and orders
- Why: High-traffic performance, fast read/write, scalable NoSQL database
- Status: Future Phase

### AWS Lambda
- Purpose: Automates confirmation emails after bookings and orders
- Why: Runs code without managing servers, pay only when triggered
- Status: Future Phase

### Amazon SNS (Simple Notification Service)
- Purpose: Sends real-time notifications to restaurant staff
- Why: Instant alerts for new bookings and orders, multiple delivery channels
- Status: Future Phase

## How It All Works Together

1. Customer visits the website (hosted on Amazon S3)
2. Customer signs in or creates an account (AWS Cognito)
3. Customer makes a booking or places an order (form data)
4. Data is stored securely (Amazon DynamoDB)
5. Confirmation email is sent automatically (AWS Lambda)
6. Restaurant staff receive a real-time notification (Amazon SNS)

## Architecture Benefits
- Scalability — handles traffic spikes automatically
- Cost-effective — pay only for what you use
- Secure — enterprise-grade AWS security
- Reliable — 99.99% uptime
- Serverless — no infrastructure to manage

## Architecture Diagram


