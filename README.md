# UDACITY Linux Configuration Project - Nils Steffensen

This README is an assignment part of the Full Stack Developer Nonadegree from Udacity, being submitted by Nils Steffensen.  It describes the deployment of the Catacity project to a Linux server, per the project submission guidelines.

## IP Address and SSH Port
The Catacity Flask app is hosted at Lightsail static IP 3.81.254.4.  SSH is accessible on port 2200 with a private RSA key placed in the submission notes.  The SSH config file for this looks like this:
```
Host lightsail 3.81.254.4
  HostName 3.81.254.4
  IdentityFile ~/.ssh/grader_rsa
  User grader
  Port 2200
```

## URL of Hosted Flask App
The Catacity Flask app can be accessed at http://www.thinknk.com.

## Summary of Software Installed and Configuration Changes
Software installed:
  * apt-get update / upgrade
  * PostgreSQL (+contrib)
  * Apache2 + WSGI (libapache2-mod-wsgi python-dev)
  * Flask, sqlalchemy, libpq-dev, psycopg2, oauth2client, requests
  * Cloned in Catalog Project

Configuration changes:
  * Add user "grader" and employ visudo to add to sudoers.  Create RSA key and add to .ssh/authorized keys.  Note, Lightsail Ubuntu instances default to no root login and no password login.
  * UFW close all ports except the specified ones.
  * Create PostgreSQL database, create user "www-data" for psycopg2 access
  * Added conf file for Apache2
  * Add .wsgi file for WSGI configuration
  * Added client_secrets.json file for Google OAuth
  
  
## Third Party Resources Used
  * Lightsail configuration panel (using "OS Only" installation)
  * DigitalOcean DNS record assignment of domain name to static IP
  * Google Console to add Javascript Origin and Redirect URI access from domain
  * Knowledge articles at DigitalOcean, GoDaddy and Stack Oberflow
  * PostgreSQL, Apache2, WSGI and Flask docs


  
