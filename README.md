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

## Getting Started

### Prerequisites

- AWS Account with appropriate permissions
- Node.js 18+
- npm or yarn
- Terraform 1.0+
- AWS CLI configured
- Stripe account for payment processing
- Twilio account for voice integration

### Local Development

1. Clone the repository:

```bash
git clone https://github.com/yourorg/ai-banking-app.git
cd ai-banking-app
```

2. Set up environment variables:

```bash
# Frontend
cd frontend
cp .env.local.example .env.local
# Edit .env.local with your configuration
```

3. Install dependencies and start the development servers:

```bash
# Backend
cd backend
npm install
npm run start:dev

# Frontend (in a separate terminal)
cd frontend
npm install
npm run dev
```

4. Access the application at http://localhost:3000

### Infrastructure Deployment

1. Initialize Terraform:

```bash
cd infrastructure
terraform init
```

2. Create a new workspace for your environment:

```bash
terraform workspace new dev
```

3. Plan and apply the infrastructure:

```bash
terraform plan -var-file=environments/dev/terraform.tfvars
terraform apply -var-file=environments/dev/terraform.tfvars
```

## API Documentation

Detailed API documentation is available in the `/docs/api` directory:

- [Authentication API](/docs/api/auth.md)
- [Users API](/docs/api/users.md)
- [Payments API](/docs/api/payments.md)
- [Documents API](/docs/api/documents.md)
- [Chatbot API](/docs/api/chatbot.md)
- [Voice API](/docs/api/voice.md)

## Development Guidelines

### Code Structure

The project follows a modular structure:
- **Frontend**: Next.js with App Router for client-side logic
- **Backend**: NestJS modules for server-side logic
- **Infrastructure**: Terraform modules for AWS resources

### Coding Standards

- Use TypeScript for type safety
- Follow the [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- Write unit tests for all business logic
- Document all public APIs and functions

### Git Workflow

1. Create a feature branch from `main`
2. Make your changes and commit with descriptive messages
3. Create a pull request to `main`
4. Ensure CI checks pass
5. Get review approval
6. Merge the pull request

## Testing

### Unit Testing

```bash
# Backend
cd backend
npm run test

# Frontend
cd frontend
npm run test
```

### End-to-End Testing

```bash
# Run e2e tests
cd frontend
npm run test:e2e
```

## Deployment

The application uses GitHub Actions for CI/CD. The workflows are defined in `.github/workflows/`:

- `infrastructure.yml`: Deploys AWS infrastructure with Terraform
- `deploy-backend.yml`: Builds and deploys the NestJS backend
- `deploy-frontend.yml`: Builds and deploys the Next.js frontend

## Security Considerations

- AWS WAF protects the API Gateway
- All data is encrypted at rest and in transit
- Proper CORS settings are configured
- Security headers are enforced in CloudFront
- Least privilege IAM policies are applied
- Regular security scanning is implemented

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Create a pull request

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.