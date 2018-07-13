# Linux Server Configuration Project

Information below represents steps which needs to be completed in order to run
Flask application with PostgreSQL database on Ubuntu 16.04 VPS.

## Technical details

### Access via SSH

__IP:__  18.130.153.115

__Port:__ 2200

__User:__ grader

__Authentication:__ using rsa key

### Accessing Web Application

__URL:__ http://18.130.153.115.xip.io

## Project completion steps

1. Create Lightsail account. 
Start on it **OS Only** VPS with Ubuntu 16.04.
Some instructions are at <https://cloudacademy.com/blog/how-to-set-up-your-first-amazon-lightsail/>

2. Create **grader** user and manage his permissions. Update firewall settings.
Information on how to achieve that could be obtained from the respective 
Udacity's course <https://www.udacity.com/course/configuring-linux-web-servers--ud299>

3. Follow [instruction from Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)
to clone your __Catalog App__ and run it on the server with Apache2.

4. If project was developed to use _SQLite_ instead of _PostgreSQL_ few additional
 actions may be required. You may follow [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-16-04)
 to install PostgreSQL. Then path to database needs to be update in the source
 code.

5. If you perform all steps as required following list of Ubuntu packages should be installed on your VPS:

* libapache2-mod-wsgi 

* python-dev

* python-pip

* postgresql 

* postgresql-contrib

All project-specific requirements should be installed with virtualenv by using pip to get libraries from `requirements.txt` file.
 
6. If project using OAUTH from Google or Facebook authorized Javascript origins
needs to be updated to allow requests from the App's new url.

7. That's mainly it. Don't forget to restart __apache2__ service once all 
changes will be done to the project.


#### N.B.

If you having some issues running your App on Ubuntu VPS - check Python version
compatibility. I had app developed with Python 3.6 whereas Ubuntu 16.04 has 
Python 2.7 as a default one. It results in some errors since part of the features
wasn't supported.

#### N.B.2

If you can't access your Lightail instance with .pem key to continue configuration
 it could be an IP blocking issue. In my case I should use VPN to access Lightsail's
 server.
