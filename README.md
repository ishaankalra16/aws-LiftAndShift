# Vprofile-Project

A demo application deployed on AWS with the help of EC2 instances, Elastic Load Balancer, Route 53, Auto Scaling Groups and Amazon Certificate Manager.

# Provisioning 

Services:
 1. Tomcat
       Application Server
 2. RabbitMQ
       Broker/Queuing Agent
 3. Mamcache
       DB cache
 4. MYSQL
       SQL Database

# Technologies Used
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- MySQL

# Architecture 

![Screenshot (315)](https://user-images.githubusercontent.com/68735863/151652213-fd3b50c8-a8c4-4e86-8465-b2249e61afc8.png)

Users can view the application with the help of a URL. This URL will then be pointed to an endpoint, whose entry will be made in the DNS configuration of the domain. This endpoint will be used to connect to the Application load balancer using HTTPS protocol. The certificate for the same will be mentioned in the Amazon Certificate Manager. The load balancer will be configured with a security group that will only allow HTTPS traffic. With the help of Route 53 in AWS, the requests made to the load balancer endpoint will be routed to the tomcat instances. The instances running tomcat services for the project will be managed by the Auto Scaling Group and will run on a separate security group that will only allow traffic only on port 8080 from the load balancer. This application needs backend services and their backend server IP address will be mentioned in Route 53 private DNS. Also, the backend services will have a separate security group that will allow traffic within themselves and from tomcat instances on the desired ports of the services.  

# Configuration 

User data for all the instances are present in the userdata directory. These can be run either as bash scripts or as user data while launching instances. 

# Database
Here,we used Mysql DB 
MSQL DB Installation Steps for Linux ubuntu 20.04:
- $ sudo apt-get update
- $ sudo apt-get install mysql-server

Then look for the file :
- /src/main/resources/accountsdb
- accountsdb.sql file is a mysql dump file.we have to import this dump to mysql db server
- > mysql -u <user_name> -p accounts < accountsdb.sql
