## demo app - developing with Docker

This demo app shows a simple user profile app set up using 
- index.html with pure js and css styles
- nodejs backend with no database

All components are docker-based

### With Docker

#### Steps to Create image, Container & run the application

Step 1: clone this git repository on your AWS Linux EC2 instance using below command

    git clone https://github.com/kukrejashyam/docker-c3-app-nodb.git 

Step 2: Go inside "docker-c3-app-nodb" directory 

    cd docker-c3-app-nodb   

Step 3: Build the version-1 app image with the name "c3-app-nodb" and tag 1.0 using below command
    
    docker build . -t c3-app-nodb:1.0   

Step 4: Create a container from the above created image "c3-app-nodb:1.0" and expose it to port 9003 using below command.

    docker run -d -p 9003:3000 c3-app-nodb:1.0

_NOTE: Don't forget to open this port 9003 in security group of respective EC2 instance in your AWS account_

Step 5: Now access the below URL in the browser

    http://ec2-public-ip:9003
    e.g.  http://184.72.185.255:9003

_NOTE: Copy the correct Public IP of this EC2 instance from your AWS account_

