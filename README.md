# AI Banking Application

![AWS Infrastructure](https://img.shields.io/badge/AWS-Infrastructure-orange)
![Next.js](https://img.shields.io/badge/Frontend-Next.js_14-blue)
![NestJS](https://img.shields.io/badge/Backend-NestJS-red)
![Terraform](https://img.shields.io/badge/IaC-Terraform-purple)
![AWS Bedrock](https://img.shields.io/badge/AI-AWS_Bedrock-green)

A production-ready AI banking application built with AWS cloud services, featuring an AI-powered chatbot, document processing, and voice agent capabilities.

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Local Development](#local-development)
  - [Infrastructure Deployment](#infrastructure-deployment)
- [API Documentation](#api-documentation)
- [Development Guidelines](#development-guidelines)
- [Testing](#testing)
- [Deployment](#deployment)
- [Security Considerations](#security-considerations)
- [Contributing](#contributing)
- [License](#license)

## Overview

This application provides a modern cloud-based platform that combines financial technology with AI capabilities. It includes a tiered membership model, document processing, AI-powered chatbot, and voice agent functionality.

## Architecture

The application follows a modern cloud-native serverless architecture:

### Frontend
- Next.js 14+ application with TypeScript
- Hosted on S3 with CloudFront CDN
- Domain management with Route53
- Responsive design with component-based architecture

### Backend
- NestJS application with TypeScript
- Deployed as Lambda functions behind API Gateway
- Domain-driven design with modular architecture
- RESTful API endpoints

### Authentication
- AWS Cognito for user management
- Support for social identity providers (Google, GitHub, Apple)
- Role-based access control system

### Data Storage
- DynamoDB for user data, documents, and conversations
- S3 for document storage
- OpenSearch for vector database (semantic search)

### AI & Processing
- AWS Bedrock for language models
- AWS Textract for document text extraction
- OpenSearch for document embedding storage and retrieval

### Payment Processing
- Stripe integration for subscription management
- Tiered membership model
- Webhook handling for subscription events

### Communication
- Twilio integration for voice agent functionality
- Event-driven architecture for notifications

### DevOps
- Infrastructure as Code using Terraform
- CI/CD pipeline with GitHub Actions
- Comprehensive monitoring with CloudWatch

## Features

### User Management
- User registration and authentication
- Social login options
- Role-based access control
- Password reset functionality

### Membership Tiers
- **Basic (Free)**: Limited document uploads, basic chatbot features
- **Advanced ($20 AUD/month)**: Increased limits, additional customization
- **Pro ($50 AUD/month)**: Unlimited features, Twilio integration

### Document Processing
- Upload DOCX and PDF documents
- Automatic text extraction
- Document indexing for AI retrieval
- Document management with version control

### AI Chatbot
- Context-aware conversations
- Document-based question answering
- Personalized responses based on user history
- Customizable chatbot behavior

### Voice Agent
- Phone-based interaction using Twilio
- Voice-to-text and text-to-voice capabilities
- Call routing and escalation paths
- Integration with chatbot backend

### Admin Features
- User management
- Role assignment
- Usage analytics
- System health monitoring