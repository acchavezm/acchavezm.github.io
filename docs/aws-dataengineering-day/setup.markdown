---
layout: page
title: Setting up
permalink: /aws-dataengineering-day/setup
parent: Data Engineering Immersion Day
nav_order: 1
---

# Setup
## Steps
- Introduction
- CloudFormation Stack Deployment
- Set up the Amazon Kinesis Data Generator
- Set up Email and SMS Subscription
- Observe AWS Lambda Anomaly function
- Appendix: CloudFormation Template

## Introduction
This guide will help you set up the pre-lab environment for the Real-Time Clickstream Anomaly Detection Amazon Kinesis Data Analytics lab.

/* TODO - ask for clarification */ The AWS CloudFormation template Kinesis_PreLab.yaml (optionally copy YAML code from the end of this page) included with this lab deploys the following architecture without the highlighted components. You will set up the highlighted components manually.
This is the child.

![Sample architecture](https://static.us-east-1.prod.workshops.aws/public/2e62dc4a-2508-425d-ab74-0e32e82672e2/static/300/images/1.png)

After you deploy the CloudFormation template, sign into your account to view the following resources:

Two Amazon Simple Storage Service (Amazon S3) buckets: You will use these buckets to persist raw and processed data.
One AWS Lambda function: This Lambda function will be triggered once an anomaly has been detected.
Amazon Simple Notification Service (Amazon SNS) topic with an email and phone number subscribed to it: The Lambda function will publish to this topic once an anomaly has been detected.
Amazon Cognito User credentials: You will use these user credentials to log into the Kinesis Data Generator to send records to our Amazon Kinesis Data Firehose.