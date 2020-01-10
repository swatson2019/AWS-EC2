# AWS setting up EC2
## Build virtual machine by setting up an instance

- configure instance - enable auto-assign public ip
- add tag - "Name" and "Sam-Watson-eng-48-test"
- configure security - set up which ip addresses can access machine
port 22 for ssh, 80 & 8080 for web access
- either create new key pair or use created one to allow access to machine - download and move to ssh folder in /users/SamWatson/.ssh

## Connect to machine created on AWS with key created
ssh -i ~/.ssh/sam-watson-eng-48-test.pem ubuntu@63.33.51.84

## Copying Files (provision.sh) Between Local Computer and Instance (AWS)
- To use scp(simply copy) with a key pair use the following command: scp -i ~/.ssh/sam-watson-eng-48-test.pem app/provision.sh ubuntu@63.33.51.84:/home/ubuntu/app-provision.sh

## To run bin file in gitbash terminal
- First go into machine as shown above and then cd /home/ubuntu
- ./app-provision.sh

## Copying entire directory (environment/app) between local computer and instance (AWS) in bash
- scp -i -r <path to key> <folder wanting to copy> <machine@publicip>:path to location on vm   you want to copy folder to
- scp -i -r ~/.ssh/sam-watson-eng-48-test.pem app ubuntu@63.33.51.84:/home/ubuntu/app

## Adding execute writes to provision file within db within machine
- cd /home/ubuntu/environment
- chmod +x provision.sh

## Terminate AWS machine
- navigate to aws ec2 instance page
- select Instance
- select actions - instance state - stop - terminate
#test1234567891011
