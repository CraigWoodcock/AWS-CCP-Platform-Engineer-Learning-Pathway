# Auto Scaling Groups

## Creating an Auto Scaling Group

1. Log into AWS and search for "Auto Scaling Groups"
2. Select "Create Auto Scaling Group"
3. Enter a name.
4. Select a "Launch Template" if you have one available, if not, select "Create a launch template" nd a new tab will be opened.

     -  Give LT a name
     -  Select your 'AMI' - We will be using 'Amazon Linux' 
     -  Select your 'Instance type' - T2.micro
     -  Select or Create a Security Group
     -  Expand 'Advanced Details' scroll down to user data and paste this script:
     -  This installs Apache web server.

    ```
    #!/bin/bash
    # install httpd
    yum update -y
    yum install -y httpd
    systemctl start httpd
    systemctl enable httpd
    echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
    ```
     - Select 'Create Launch Template'

5. Now close the current tab and go back to the previous tab
6. Select your launch template from the dropdown box
   - You may need to press the refresh button to populate the list.
   - Press 'Next'
7. Use the 'Default VPC' for this project
8. Select ALL 'Availability Zones' (1a, 1b, 1c).
   - press 'Next'
9. Select 'Attach to an existiing load balancer' if you have one.
   - We are going to 'Attach to a new Load Balancer'
   - Select 'Application Load Balancer'
   - Rename the Load Balancer 
   - Select 'Internet Facing' so that it can be accessed by public traffic
   - select or create a 'target group' on port 80
   - We will create one here - give it a name
10. Turn on 'Elastic Load Balancing health checks'
    - set delay time for the first health check
    - Leave at 300(5mins) if unsure.
    - press 'Next'
11. We need to Enter our desired capacity.
    - The Udemy Tutorial tells us to enter 1 here but this does not achieve 'High Availability' so we will set it to 2.
    - We will set the minimum at 2 and the max at 3 - Again to achieve 'High Availability
12. Select 'Target tracking scaling policy'
    - Select metric to measure
    - set value (%)
    - uncheck 'Disable scale in to create only a scale-out policy'
13. Under 'Instance Maintenance'
    - Select 'Launch before terminating'
    - press 'Next' until we get to 'Tags'
14. Add a new Tag:
    - Key = Name
    - Value = Unique name for your EC2 instances i.e. "Demo-ASG-HA-SC-VM"
15. Create your ASG!
  
In order to see the results we can use the DNS name assigned to the load balancer in the web browser.

Every time we refresh we will see a different IP Address printed to the web page. This is because the load balancer evenly distributes traffic across the instances.

![Alt text](<Screenshots/Screenshot 2024-01-23 150325.png>)
![Alt text](<Screenshots/Screenshot 2024-01-23 150338.png>)

## Terminating the ASG and EC2 Instances

When terminating, we must delete the ASG first and then the load balancer before we can terminate the EC2's. This is because the ASG and Load balancer will try to spin up Instancs to replace the terminated instances.