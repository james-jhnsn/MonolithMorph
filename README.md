## Project Name

MonolithMorph

## Description

In this project, I successfully deployed a monolithic Node.js application to a Docker container and then decoupled it into microservices without any downtime. The application I built is a message board that allows users to interact through threads and messages.

Traditional monolithic architectures pose challenges when it comes to scalability, updates, and maintenance. As the code base grows, it becomes increasingly complex to introduce new features, languages, frameworks, and technologies, limiting innovation and flexibility.

By adopting a microservices architecture, I transformed the monolithic application into separate services, each running in its own container. This approach allows for independent scaling and updates of different application features. Microservices are designed around specific business capabilities, and each service performs a single function. Additionally, microservices can be written in different programming languages and frameworks.

Before you begin, ensure you have the following installed:

1. **AWS Account**: [Sign up here](https://aws.amazon.com/) if you don't have one.
2. **Docker**: Install for [Mac](https://docs.docker.com/docker-for-mac/install/) or [Windows](https://docs.docker.com/docker-for-windows/install/). 
   - Confirm installation with:
     ```
     docker --version
     ```

3. **AWS CLI**: 
    - [Getting Started with AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html).
    - Confirm installation:
      ```
      aws --version
      ```
    - Update if necessary:
      ```
      pip install awscli --upgrade --user
      ```

4. **AWS Copilot**: On macOS, install using brew:
    ```bash
    brew install aws/tap/copilot-cli
    ```

## Deployment Steps

1. **Initialize AWS Copilot Application**:
    ```
    cd ./amazon-ecs-nodejs-microservices/
    copilot app init
    ```

2. **Set Up Environment**:
    ```
    copilot env init
    ```
    - When prompted, name the environment `api`.

3. **Deploy the Environment**:
    ```
    copilot env deploy --name api
    ```

4. **Set Up Monolithic AWS Copilot Service**:
    ```
    copilot svc init
    ```
    - Select `Load Balanced Web Service` when prompted.
    - Name the service `monolith`.
    - Select `Enter custom path for your Dockerfile` and specify the path to `2-containerized/services/api/Dockerfile`.

5. **Deploy the Monolithic Service**:
    ```
    copilot svc deploy --name monolith
    ```

6. **Test the Deployment**: 
    Once deployed, AWS Copilot will provide a URL. Use the URL to test endpoints like:
    ```
    http://<application-string>.us-east-1.elb.amazonaws.com/api/users/3
    http://<application-string>.us-east-1.elb.amazonaws.com/api/threads/2
    ```
## Creating Microservices

After setting up the initial `api` Application and the `api` Environment, you can utilize them to deploy your microservices. This section covers the deployment of three microservices: `posts`, `threads`, and `users`.

### Step 1: Initialize the Microservices

1. **Initialize the `posts` microservice**:
   ```bash
   copilot svc init --app api --dockerfile ./3-microservices/services/posts/Dockerfile --name posts --svc-type "Load Balanced Web Service"

    Initialize the threads microservice:

copilot svc init --app api --dockerfile ./3-microservices/services/threads/Dockerfile --name threads --svc-type "Load Balanced Web Service"

Initialize the users microservice:

    copilot svc init --app api --dockerfile ./3-microservices/services/users/Dockerfile --name users --svc-type "Load Balanced Web Service"

Step 2: Configure Service Paths

AWS Copilot configures the service path based on the service name. However, you might want to adjust these paths based on your application's routing. Edit the manifest.yml of each microservice to adjust the path:

For instance, for the posts service:

http:
  path: 'api/posts'

Repeat similar configurations for threads and users services by setting their respective paths in the manifest files.

## Deploying Microservices

### **Step 1: Deploy the Microservices**

For each microservice, run the following command:


copilot svc deploy --name <microservice-name>

    Deploy posts microservice:


copilot svc deploy --name posts

### **Deploy threads microservice:


      copilot svc deploy --name threads

### **Deploy users microservice:

    copilot svc deploy --name users

### **Step 2: Shut down the Monolith

Shut down the monolithic service using:

      copilot svc delete --name monolith

### **Step 3: Verify the Deployment

You can validate the microservices deployment using the provided URLs:

    Check User Data:


http://api-a-publi-du44d9vosxla-792918025.us-east-1.elb.amazonaws.com/api/users/3

Check Thread Data:


      http://api-a-publi-du44d9vosxla-792918025.us-east-1.elb.amazonaws.com/api/threads/2

View Posts Data:


      http://api-a-publi-du44d9vosxla-792918025.us-east-1.elb.amazonaws.com/api/posts/

View Posts in Thread 1:

      http://api-a-publi-du44d9vosxla-792918025.us-east-1.elb.amazonaws.com/api/posts/in-thread/1
