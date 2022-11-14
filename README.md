This is a sample Web Application to use during Continuous Integration demos.

#Build Instruction





```
mvn3 clean package
```



#Deploy instruction



Deploy ```target/WebApp.war``` on Tomcat
 
#TODO
 
Add instruction to deploy to ElasticBeanstalk




Welcome to DevOps tutorial, 

Below are the Steps for creating Complete flow.
Create the Docker File
# Define te Image 
FROM tomcat:8-jre8
# Maintainer 
MAINTAINER "abhishek"
# Copy the war file into the tomcat webapps location 
COPY WebApp.war /usr/local/tomcat/webapps
# expose the 8080 port
EXPOSE 8080
Publish over SSH Download this Plugins and set Below Details .
Key -- define the private Key ( you will get from .pem while when you will open as text file)

ssh Server - 

Name - define the name of the server.
HostName - Provide the IP address of your server.
UserName - Provide the user name here ex. if we are using Ubuntu ec2 instance then username is ubuntu

Click Save and Apply 
Create the new FreeStyle Project
Git URL - https://github.com/Abhishek08/webapp.git

WebHook Connection URL - http://IPADDRESS/github-webhook/ (push)

BUILD - Package 
Post Build Action Define below details.
sudo mv  ./home/ubuntu/com/target/WebApp.war /home/ubuntu/com; // Copy the war file into the your Server Location 
cd /home/ubuntu/com; // Goto the Location where DockerFile is present.
docker stop mycontainer; // Stop the Container if its running 
docker rm mycontainer; // Remove the container
docker build -t myimage .; // Create the new Image using Docker file
docker run -d --name mycontainer -p 8090:8080 myimage; // Create new Container using the custom Image.


Reference : 
https://github.com/Abhishek08/Docker
