## Project

MonolithMorph

## Overview

In this project, I successfully deployed a monolithic Node.js application to a Docker container and then decoupled it into microservices without any downtime. The application I built is a message board that allows users to interact through threads and messages.

## Why this matters

Traditional monolithic architectures pose challenges when it comes to scalability, updates, and maintenance. As the code base grows, it becomes increasingly complex to introduce new features, languages, frameworks, and technologies, limiting innovation and flexibility.

By adopting a microservices architecture, I transformed the monolithic application into separate services, each running in its own container. This approach allows for independent scaling and updates of different application features. Microservices are designed around specific business capabilities, and each service performs a single function. Additionally, microservices can be written in different programming languages and frameworks.

## What I accomplished

Throughout this project, I achieved the following:

1. Containerized and deployed the monolithic application:
   - Leveraged Docker to create a container for the Node.js application.
   - Utilized AWS Copilot to set up a managed cluster of EC2 compute instances.
   - Deployed the monolithic application as a container running on the cluster.

2. Decoupled the monolith into microservices:
   - Broke down the Node.js application into multiple interconnected services.
   - Pushed each service's image to an Amazon Elastic Container Registry (Amazon ECR) repository.

3. Deployed microservices and implemented traffic shifting:
   - Deployed the Node.js application as a collection of interconnected services.
   - Utilized an Application Load Balancer (ALB) to seamlessly shift traffic from the monolith to the microservices, ensuring a smooth transition without any downtime.

## Prerequisites

To complete this project, I had the following prerequisites in place:

- An AWS account (If not available, I followed the ["Setting Up Your AWS Environment"](https://aws.amazon.com/getting-started/guides/setup-environment/) tutorial for a quick overview).
- AWS CLI installed and configured.
- AWS Copilot installed and configured.
- Docker installed.
- A text editor (I used VS Code, but any preferred IDE can be used).

## Modules

This project followed a modular structure, which consisted of the following modules:

1. Setup:
   - Installed and configured the AWS CLI.
   - Installed AWS Copilot.
   - Installed Docker.

2. Containerize and deploy the monolith:
   - Containerized the application using Docker.
   - Used AWS Copilot to instantiate a managed cluster of EC2 compute instances.
   - Deployed the monolithic Node.js application as a container running on the cluster.

3. Break the monolith:
   - Divided the Node.js application into several interconnected services.
   - Pushed each service's image to an Amazon Elastic Container Registry (Amazon ECR) repository.

4. Deploy microservices:
   - Deployed the Node.js application as a set of interconnected services behind an Application Load Balancer (ALB).
   - Implemented traffic shifting using the ALB to seamlessly transition from the monolith to the microservices.

## Technologies Used

This project utilizes the following technologies:

- **Amazon EC2**: Amazon Elastic Compute Cloud (EC2) provides resizable compute capacity in the cloud and is used to instantiate a managed cluster of EC2 compute instances.

- **Amazon ECR**: Amazon Elastic Container Registry (ECR) is a fully managed container registry service. It is used in this project to store and manage container images for the microservices.

- **Amazon ECS**: Amazon Elastic Container Service (ECS) is a highly scalable, fast, container management service. It is used to deploy and run the microservices as containers.

- **AWS Copilot**: AWS Copilot is a command-line tool that enables developers to build, release, and operate production-ready applications on AWS. It simplifies the process of building containerized applications by providing a consistent and opinionated workflow.

- **AWS Fargate**: AWS Fargate is a serverless compute engine for containers. It enables you to run containers without having to manage the underlying infrastructure. In this project, it is used as the compute engine for running the microservices.

- **Docker**: Docker is an open platform for developing, shipping, and running applications. It is used to containerize the monolithic Node.js application and each of the microservices.

- **Node.js**: Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. It is used to develop the monolithic application and the microservices.

- **VS Code**: Visual Studio Code is a lightweight, cross-platform source code editor. It is used as the preferred IDE for development in this project.

These technologies work together to enable the successful containerization, deployment, and management of the monolithic application as microservices, providing scalability, flexibility, and independent updating capabilities.
