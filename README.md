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

1. Setup (20 minutes):
   - Installed and configured the AWS CLI.
   - Installed AWS Copilot.
   - Installed Docker.

2. Containerize and deploy the monolith (30 minutes):
   - Containerized the application using Docker.
   - Used AWS Copilot to instantiate a managed cluster of EC2 compute instances.
   - Deployed the monolithic Node.js application as a container running on the cluster.

3. Break the monolith (20 minutes):
   - Divided the Node.js application into several interconnected services.
   - Pushed each service's image to an Amazon Elastic Container Registry (Amazon ECR) repository.

4. Deploy microservices (30 minutes):
   - Deployed the Node.js application as a set of interconnected services behind an Application Load Balancer (ALB).
   - Implemented traffic shifting using the ALB to seamlessly transition from the monolith to the microservices.
