# Task 14: Free VM Setup and Web Application Deployment

## Overview

In this task, I created a free virtual machine (VM) in my cloud account (AWS/GCP/Azure), set up an Apache web server, and deployed a web application to demonstrate the deployment process and user registration functionality. This README documents the steps taken, along with screenshots of the process.

## Steps Taken

1. Login to Your Cloud VM via SSH from Kali Linux
   - Open your Kali Linux terminal.
   - Use the following SSH command to log in to the VM:
     "<ssh -i /path to private_key> username@<your-vm-public-ip>"
   -  Capture a screenshot showing successful SSH login.

2. Clone the Repo from Taskten (HTML Page)
   - After logging into the VM, clone your taskten repository from GitHub:
     "git clone https://github.com/yourusername/taskten.git"

3. Copy the Cloned Files to Apache Web Server Root Directory
   - Copy the HTML and related files from the cloned taskten folder to the root directory of the Apache web server:
     "sudo cp -r taskten/* /var/www/html/"

4. Start the Apache Web Server
   - Start the Apache web server on the VM:
     "sudo systemctl start apache2"
   - Ensure the web server is running by checking its status:
     "sudo systemctl status apache2"

5. Access the Web Page via Local Browser
   - Open a web browser on your local machine and enter the public IP of your cloud VM:
     "http://<your-vm-public-ip>"
   - Capture a screenshot of the webpage being served from the cloud VM.

6. Install PHP and MySQL on the VM
   - If PHP and MySQL are not already installed, use the following commands to install them:

   Install PHP:
    "sudo apt update"
    "sudo apt install php libapache2-mod-php"
   
   Install MySQL:
    "sudo apt install mysql-server"

7. Start MySQL Server and Login
   - Start the MySQL service:
   "sudo systemctl start MySQL"
   - Login to MySQL as the root user:
   "sudo mysql -u root -p"

8. Create Database, Table, and User
   - Inside the MySQL shell, create a database, table, and user using the following commands:

   - Create a Database:
     "CREATE DATABASE userdb;"
     "USE userdb;"

   - CREATE TABLE users (
    ->     id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    ->     first_name VARCHAR(30) NOT NULL,
    ->     last_name VARCHAR(30) NOT NULL,
    ->     email VARCHAR(100) NOT NULL UNIQUE,
    ->     phone_number VARCHAR(15) NOT NULL,
    ->     password VARCHAR(255) NOT NULL,
    ->     reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    -> );


   - Take a screenshot showing the creation of the database, table, and user in MySQL.

9. Create/Register a User via PHP Script
   - Write or copy a PHP registration script that allows users to register their details (username, email, password) and stores them in the users table.
   - Ensure the registration form connects to the MySQL database and inserts data correctly.
   - Test the registration page by accessing it from your browser:
     "http://<your-vm-public-ip>/register.php"

10. Login as the Created User
    - After registering a new user, log in using the same credentials.
    - Take a screenshot showing the successful login page.

11. Share the Public IP of Your Web Server
    - Share your web server’s public IP with friends or colleagues to verify if they can access the registration and login pages.

## Public IP
- The public IP address of the VM is: `20.204.96.89`

## Conclusion
This task demonstrated the process of setting up a free VM, deploying a web application, and creating a user registration system. The web application is now accessible to anyone using the public IP.
