# mplemented deployment in monolithic & microservices architecture using AWS EC2 (t2-micro) instances with Ubuntu AMI. For monolithic, WordPress & MySQL were co-deployed on a single instance; for microservices, split between two EC2 instances—one for WordPress and one for MySQL. Configured security groups and created a welcome page as the homepage in WordPress. 

# infotrixTask
cloud (aws) Internship task 1
# Install apache server
 sudo apt install apache2
# Install php runtime and php mysql connector
sudo apt install php libapache2-mod-php php-mysql
# Install MySQL server
sudo apt install mysql-server 
# Login to MySQL server 
sudo mysql -u root
# change authentication plugin to mysql_native_password 
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'venky123';
# Create a new database user for wordpress  
CREATE USER 'wp_user'@localhost IDENTIFIED BY 'venky123';
# Create a database for wordpress 
CREATE DATABASE wordpress;
# Grant all privilges on the database 'wordpress' to the newly created user 
GRANT ALL PRIVILEGES ON wp.* TO 'wordpress_user'@localhost;
# Download wordpress
cd /tmp
wget https://wordpress.org/latest.tar.gz
# Unzip above tar file 
tar -xvf latest.tar.gz
# Move wordpress folder to apache document root
 sudo mv wordpress/ /var/www/html
# Restart/reload apache server
sudo systemctl restart apache2
