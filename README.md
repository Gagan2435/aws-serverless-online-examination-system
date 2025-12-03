Serverless Online Examination System

A fully serverless online examination system built using AWS services. The application allows students to attempt exams, submit answers, and instantly receive scores—without managing any servers.

Features

Displays exam questions from a secure backend

Students submit answers online

Automatic scoring using Lambda

Stores exam attempts and scores

Fully serverless, scalable, and low-cost

Secure architecture using IAM and OAC

Architecture Overview

The application follows a serverless workflow:

Static website hosted on Amazon S3

CloudFront delivers frontend securely and efficiently

API Gateway provides HTTPS endpoints

Lambda functions process backend logic

DynamoDB stores exams and student scores

CloudWatch captures logs for debugging and monitoring

AWS Services Used
Compute

AWS Lambda

Backend logic

getQuestions — returns questions without correct answers

submitExam — evaluates submitted responses and saves score

API

Amazon API Gateway

GET /exams/{examId}/questions

POST /exams/{examId}/submit

Handles input/output formatting and CORS

Database

Amazon DynamoDB

Stores exam questions

Stores student attempts and calculated results

Storage + CDN

Amazon S3 — Hosts HTML, CSS, JS (frontend)

Amazon CloudFront — Provides CDN, applies OAC for secure private-bucket access

Security & Monitoring

IAM Roles & Custom Policy — Only required DynamoDB + CloudWatch access

CloudWatch — Logs Lambda executions

Implementation Steps

Created DynamoDB tables: Exams, Attempts

Developed Lambda functions: getQuestions, submitExam

Configured API Gateway with CORS enabled

Hosted frontend files in S3

Created CloudFront Distribution with Origin Access Control (OAC)

Connected CloudFront to S3 for secure content delivery

Tested workflow end-to-end:

Questions displayed correctly

Answer submission processed

Score saved to DynamoDB

Why Serverless

No EC2 instances

No manual scaling or server maintenance

Pay-per-use model

Fully managed database and compute

Highly scalable and secure
