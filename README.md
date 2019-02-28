# Linux_Server_Configuration
This is the final project for Udacity's Full Stack Web Developer Nanodegree.

This page explains how to secure and set up a Linux distribution on a virtual machine, install and configure a web and database server to host a web application.

1.The Linux distribution is Ubuntu 16.04 LTS.

2.The virtual private server is Amazon.

3.The web application is my Item Catalog project created earlier in this Nanodegree program.

4.The database server is PostgreSQL.

# Get Server
Step 1: Start a new Ubuntu Linux server instance on Amazon EC2
   
   Login to aws.amazon.com and login to default user (ubuntu)
   
   Choose EC2 and Launch Instance with appropriate settings.
   
   Check for instance IPv4 public IP - 3.87.52.54

   we can download a .pem file and connect with following command
   
   ssh -i ItemCatalog_19_01_2019.pem ubuntu@54.161.86.157
   
   22 is Port by Default,Later we need to change it to 2200 as per the udacity-linux-server-configuration rubrics.


# Secure Server

Step 2: Update and upgrade installed packages
   sudo apt-get update
   
   sudo apt-get upgrade
   
Step 3: Change the SSH port from 22 to 2200

   Edit the /etc/ssh/sshd_config file: sudo vi /etc/ssh/sshd_config.
   
   Change the port number on line 5 from 22 to 2200.
   
   Save and exit using esc and confirm with :wq.
   
   Restart SSH: sudo service ssh restart.
   
   Change inbound rules in Amazon EC2 --> Type : Custom TCP Rule as 2200

   To check port 2200 wether working or not by ssh -i ItemCatalog_19_01_2019.pem -p 2200 ubuntu@54.161.86.157
