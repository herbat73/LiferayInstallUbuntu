# 2. Installing MySQL

On Ubuntu 16.x, only the latest version of MySQL is included in the apt package repository by default. At the time of writing, that's MySQL 5.7.16

The simplest way is typing

`sudo apt-get install mysql-server`

On package configuration enter the password for the MySQL root user.

![](/assets/mysql_pass.png)

Type and remember it. You will use it later.

Install security script in order to remove remote root login and sample users.

`sudo mysql_secure_installation`

You will be asked to enter MySQL root password which you have entered during installation process and latter choose `Y` to accept all default security options.

Test MySQL installation by typing

`systemctl status mysql.service`

You should get response like

`● mysql.service - MySQL Community Server`

`Loaded: loaded (/lib/systemd/system/mysql.service; enabled; vendor preset: en`

`Active: active (running) since Tue 2017-01-03 20:01:19 UTC; 22min ago`

`Main PID: 11230 (mysqld)`

`CGroup: /system.slice/mysql.service`

`└─11230 /usr/sbin/mysqld`

`Jan 03 20:01:18 myhost systemd[1]: Starting MySQL Community Server...`

`Jan 03 20:01:19 myhost systemd[1]: Started MySQL Community Server.`

You can also try to connect to the database by using mysqladmin tool.

For an example if you want to get version of mysqladmin you can type

`mysqladmin -p -u root version`

After entering password for MySQL user you will get information like

`mysqladmin  Ver 8.42 Distrib 5.7.16, for Linux on x86_64`

`Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.`

`Oracle is a registered trademark of Oracle Corporation and/or its`

`affiliates. Other names may be trademarks of their respective owners.`

`Server version        5.7.16-0ubuntu0.16.10.1`

`Protocol version    10`

`Connection        Localhost via UNIX socket`

`UNIX socket        /var/run/mysqld/mysqld.sock`

`Uptime:            27 min 45 sec`

`Threads: 1  Questions: 12  Slow queries: 0  Opens: 115  Flush tables: 1  Open tables: 34  Queries per second avg: 0.007`

Now, you can create Liferay database. Enter mysql command tool by typing

`mysql -u root -p`

Create `lportal` database by entering sql script

CREATE DATABASE lportal CHARACTER SET utf8 COLLATE utf8\_general\_ci;

MySQL will execute script and give you response like

`Query OK, 1 row affected (0.00 sec)`

Type `exit` to quite mysql tool.



