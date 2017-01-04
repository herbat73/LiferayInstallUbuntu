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

Now we need to install additional proxy and rewrite modules for Apache

`sudo a2enmod proxy`

`sudo a2enmod proxy_http`

`sudo a2enmod rewrite`

And one more for plug-in that handles the communication between Tomcat and Apache.

`sudo apt-get install libapache2-mod-jk`

Restart apache service to enable installed modules

service apache2 restart

You can be asked for entering sudo password.

We need to configure the JK module. Edit the configuration file located at /etc/libapache2-mod-jk/workers.properties

Open in text editor with sudo privelages like

sudo nano /etc/libapache2-mod-jk/workers.properties

Inside the the file find find the`workers.tomcat_home` parameter.

Originally it is setup like

`workers.tomcat_home=/usr/share/tomcat8`

You should change it to your Liferay tomcat home. In our case it should be

`workers.tomcat_home=/home/myusername/liferay-ce-portal-7.0-ga3/tomcat-8.0.32`

Adjust the value to your particular username and installation folder.

Save the file.

Now, we will modify apache http port to forward handles to tomcat worker.

Open apache config file /etc/apache2/sites-available/000-default.conf

sudo nano /etc/apache2/sites-available/000-default.conf

Add line JKMout for instance after DocumentRoot

`<VirtualHost *:80>`

`...`

`ServerAdmin webmaster@localhost`

`DocumentRoot /var/www/html`

`JKMount /* ajp13_worker`

`..`

`</VirtualHost>`



## Step 2 - Create reverse proxy

## 

## Step 3 - Set Up the SSL Certificate



