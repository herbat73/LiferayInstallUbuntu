# 4. Encrypting Tomcat Connections with Apache

Follow these steps in order to setup a SSL-enabled proxy to secure user connection with Tomcat server.

We will use reverse proxy model. The Apache web server will handle request with Let's Encrypt free SSL certifcates and then proxy requests to Liferay running on Tomcat server.

## Step 1 - Install Apache server

You can get Apache installed on your server through`apt-get`

Enter command

`sudo apt-get install apache2`

You can test if Apache server is running by entering in the browser ip address of your server.

You should see Apache welcome screen.

![](/liferey_installation_ubuntu/assets/apache_ubuntu.png)

Alternatively you can check if server is running on port 80 by using netcat tool

`nc -zv localhost 80`

It should give you response

`Connection to localhost 80 port [tcp/http] succeeded!`

Now we need to install additional modules for Apache



## Step 2 - Create reverse proxy

## 

## Step 3 - Set Up the SSL Certificate



