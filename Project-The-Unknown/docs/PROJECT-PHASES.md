# Project Phases

## Overview
The Unknown restaurant website is being built in phases. Each phase adds new functionality, building on top of the previous one.

## Phase 1: Static Website on S3 ✅ (Completed)
- Build the HTML, CSS, and JavaScript website
- Create all 4 pages (Home, Booking, Order, Confirmation)
- Host the website on Amazon S3
- Configure S3 for static website hosting
- Test the website is accessible via the S3 URL

## Phase 2: User Authentication (AWS Cognito)
- Set up AWS Cognito User Pool
- Add sign-up and login functionality
- Allow customers to create accounts
- Enable customers to view their booking history
- Secure pages behind authentication

## Phase 3: Database Integration (Amazon DynamoDB)
- Create DynamoDB tables for bookings and orders
- Store customer profiles securely
- Connect booking form to DynamoDB
- Connect order form to DynamoDB
- Enable data retrieval for staff dashboard

## Phase 4: Automated Emails (AWS Lambda)
- Create Lambda function for confirmation emails
- Trigger email when a booking is submitted
- Trigger email when an order is placed
- Include booking/order details in the email
- Set up Amazon SES for email delivery

## Phase 5: Staff Notifications (Amazon SNS)
- Set up SNS topic for restaurant staff
- Send real-time alerts when new bookings arrive
- Send real-time alerts when new orders are placed
- Allow staff to subscribe via email or SMS
- Configure notification preferences

## Phase 6: Analytics and Reporting
- Track number of bookings per day/week/month
- Track popular menu items
- Monitor peak booking times
- Generate reports for restaurant management
- Use data to improve customer experience

## Current Status
- Phase 1: ✅ Complete
- Phase 2: ⏳ Planned
- Phase 3: ⏳ Planned
- Phase 4: ⏳ Planned
- Phase 5: ⏳ Planned
- Phase 6: ⏳ Planned
