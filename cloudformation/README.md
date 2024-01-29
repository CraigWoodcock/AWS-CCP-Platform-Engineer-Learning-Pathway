# CloudFormation

- [CloudFormation](#cloudformation)
  - [What is CloudFormation](#what-is-cloudformation)
  - [Benefits of CloudFormation](#benefits-of-cloudformation)
  - [Using CloudFormation](#using-cloudformation)


## What is CloudFormation

![CloudFormation](<Screenshots/Screenshot 2024-01-29 144754.png>)

## Benefits of CloudFormation

- Infrastructure as Code
  - no resources are manually created - great for control
  - Changes to infrastructure are reviewed through code
- Cost 
  - Resources within a stack are tagged so you can track costs
  - Estimate costs using CloudFormation template
  - Savings Strategy - automate deletion and creation of templates safely 
- Productivity
  - Destroy and create infrastructure on the cloud on the fly
  - Automated generation of Diagram for you rtemplates
  - Declarative programming - no need to figure out ordering and orchestration
  - Leverage existing templates and documentation
- Support
  - Almost all AWS services are supported
  - 'Custom Resources' can be used for resources that are not supported

## Using CloudFormation

1. Create a Stack
  - Sign into AWS and go to 'CloudFormation'
  - Ensure the correct Regoin is selected (we are using us-east-1)
    - Select 'Create a stack'
    - Select 'Template is ready'
    - Upload file [EC2-Only.yml](0-just-ec2.yaml)
      - This creates an EC2 Instance
      - An S3 bucket will be createed to store the file
    - Press 'Next' and give the Stack a name
    - Press 'Next' and give it a Tag
    - Review and Create the template
2. Update the stack template
   - press 'Update'
   - Select new file [EC2 and Security Groups](1-ec2-with-sg-eip.yaml)
     - This creates an EC2, 2 Security groups and an Elastic IP
   - Review and update stack  


- Deleting the stack will remove all stack resources that have been created.
    