# About
The purpose of this project is to a set up a Linux server to host
a catalog project for Udacity's FullStack Nanodegree Program.

# Technical Information
IP Address: http://18.221.98.183/

(Use site with URL, otherwise Goolge login does not work)

URL: http://ec2-18-221-98-183.us-east-2.compute.amazonaws.com/

# SSH Information
SSH Port: 2200

The SHA key-pair is sent to the reviewer in a .zip file.

The zipped file contains the public key and private key.

# Directions for SSH Connection

1. Download and open zipped file

2. In a Linux machine, do the following

   sudo touch /home/yourusername/.ssh/grader
   
   sudo touch /home/yourusername/.ssh/grader.pub

3. sudo nano /home/yourusername/.ssh/grader.pub

   Paste the public key located in the zipped file in Details.txt

4. sudo nano /home/yourusername/.ssh/grader

   Paste the private key located in the zipped file in SSH Private Key.txt

5. ssh grader@18.221.98.183 -p 2200 -i ~/.ssh/grader

You should connect to the server with sudo privs

# Summary of Software Installed

The following software is installed in the server:
    - Flask
    - Psycopg2
    - SQLAlchemy
    - Apache2
    - WSGI
    - PostgreSQL
    - Oauth2Client
    - git

# Summary of Configurations

- The server firewall only allows traffic through ports 80, 123, 2200.
- The SSH port is 2200
- There are two created user with sudo access; student, grader
- Remote Root login is not allowed, and password remote login is not permitted
- The apache2 server uses WSGI to run a flask app located in /var/www/FlaskApp/CRUD_Project_Udacity
- PostgreSQL is used to store data for catalog project
- The PostgreSQL database is set to user catalog.
- Catalog user is not a superuser, and database can be accessed with sudo -u catalog psql
- As of 4/16/18 all packages are updated

#  Third-Party Resources Used
  DigitalOcean.com was used for apache2 server configuration 

- https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps

- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04
