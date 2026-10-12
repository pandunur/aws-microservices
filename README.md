# AWS Microservices Project

A hands-on, production-inspired microservices architecture built on AWS using Docker, Amazon ECR, ECS Fargate, and Application Load Balancer. CI/CD pipeline to automate pushing images to ECR and deploy with ECS Fargate.

## Architecture

![AWS Microservices Architecture](docs/architecture-diagram.png)

## Architecture Overview

The application consists of three independent microservices:

- User Service
- Payment Service
- Notification Service

Each service is containerized with Docker and deployed independently using ECS Fargate.

The services run in private subnets and are accessed through an internet-facing Application Load Balancer.

### Request Flow

```text
Internet
    |
    v
ALB :80
    |
    +-- /users ---------> user-service :8080
    |
    +-- /payments ------> payment-service :8080
    |
    +-- /notifications -> notification-service :8080
