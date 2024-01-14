# How to SSH into the EC2 Instance
1. Ensure the Key File is in the .ssh folder
2. Open CLI of your choice, I use 'Git Bash'
3. Run `ssh -i "~/.ssh/name-of-key" user@ip` 
 - This can be copied from the 'Connect' tab within the instance details.
4. Type 'yes' to add fingerprint and you will be connected!