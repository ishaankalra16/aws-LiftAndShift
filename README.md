A demo application deployed on AWS with the help of EC2 instances, Elastic Load Balancer, Route 53, Auto Scaling Groups

# Architecture 

![Screenshot (315)](https://user-images.githubusercontent.com/68735863/151652213-fd3b50c8-a8c4-4e86-8465-b2249e61afc8.png)

# Technologies Used
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- MySQL
# Database
Here,we used Mysql DB 
MSQL DB Installation Steps for Linux ubuntu 14.04:
- $ sudo apt-get update
- $ sudo apt-get install mysql-server

Then look for the file :
- /src/main/resources/accountsdb
- accountsdb.sql file is a mysql dump file.we have to import this dump to mysql db server
- > mysql -u <user_name> -p accounts < accountsdb.sql


