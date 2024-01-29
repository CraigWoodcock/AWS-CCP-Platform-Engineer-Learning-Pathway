# ECS, Fargate & ECR Overview

## ECS
  - Elastic Container Service
  - Used to launch Docker Containers on AWS
  - We need to create EC2 instances in advance
  - AWS takes care of stopping/starting the instances
  - ECS can intergrate with an application load balancer so we can create web applications.
  - Automaticaslly places docker container on suitable EC2 instances.   
    - Diagram shows ECS distributing containers between EC2's
  
    ![ECS Diagram](<../Screenshots/Screenshot 2024-01-29 103006.png>)

## Fargate
  - Used to launch Docker Containers on AWS
  - We don't need to create EC2 instances in advance - Fargate does this for us.
  - Serverless - because we dont need to manage the servers
  - AWS runs containers based on CPU/RAM that is needed
    - Diagram shows container being created and Fargate<br> handles everything else.  

    ![Fargate Diagram](<../Screenshots/Screenshot 2024-01-29 104133.png>)

## ECR
  - Elastic Container Registry
  - Private docker Registry (repo) on AWS
  - This is where you store your Docker Images so that can be run by ECS or Fargate
    - Diagram shows Fargate Creating containers using ECR

    ![Fargate Diagram](<../Screenshots/Screenshot 2024-01-29 115934.png>)
  
