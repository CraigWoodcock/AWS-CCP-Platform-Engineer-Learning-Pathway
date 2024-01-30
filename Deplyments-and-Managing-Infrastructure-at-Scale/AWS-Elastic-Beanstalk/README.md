# AWS Elastic Beanstalk

## What is Elastic Beanstalk


## Deploying Web Application Using Beanstalk

- sign into AWS and go to 'Elastic Beanstalk'
- Select 'Create Application'
- Give it a name
- name the environment e.g. MyApplication-dev
- choose a platform:
  - platform = 'Java'
  - platform branch = 'Corretto 17 64bit Amazon Linux 2023'
  - version = 'recommended'
- Select sample application or upload your own:
  - I will use my own.
  - choose a version - I'll say 0.0.1.
  - upload file - I will use my Java movie database application:
    - [Java-Spring-API.jar](Extras/springapi-0.0.1-SNAPSHOT.jar)
- Select Single Instance on this occasion
- Press 'Next' 

- We may need to create an EC2 Instance Profile:
  - Go to IAM
  - Select 'Roles'
  - Select 'Create Role'
  - Select 'AWS Service'
  - Select 'EC2'
  - Press 'Next'
  - Select WorkerTier, WebTier, MultiContainerDocker
  - Enter aws-elastic-beanstalk-ec2-role for the role name
  - Select 'Create role'

- Back in Beanstalk configuration
- Select Service Role
- Select EC2 Instance Profile that we created in the previous step
- Select 'Skip to review'
- Select 'Submit'


- When the status of the environment is 'OK', we can go to domain Name of the environment to see the application working:


![Deployed via Beanstalk](<Extras/Screenshot 2024-01-30 151642.png>)