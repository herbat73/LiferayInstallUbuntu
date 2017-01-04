# 1. Components installation

## 1.1 Update Ubuntu to the newest version

First, update the package index.

`sudo apt-get update`

`sudo apt-get upgrade`

## 2. Installing the JRE/JDK

The easiest way is installing Java by using version packaged with Ubuntu. Following steps will install OpenJDK 8.

This command will install the Java Runtime Environment \(JRE\).

`sudo apt-get install default-jre`

After installation you can validate it by entering command

`java -version`

It should give you response with installed Java version like

`openjdk version "1.8.0_111"`

`OpenJDK Runtime Environment (build 1.8.0_111-8u111-b14-2ubuntu0.16.10.2-b14)`

`OpenJDK 64-Bit Server VM (build 25.111-b14, mixed mode)`

If you are going to compile Java programs, deploy portlets please install JDK \(Java Development Kit\).

Please notice JDK does contain JRE so you can only install JDK to get the system running.

`sudo apt-get install default-jdk`

Validate JDK installation by entering command

`javac -version`

It should give you response with JDK version like

`javac 1.8.0_111`

Set JAVA\_HOME enviroment variable by opening environment file

`sudo nano /etc/environment`

add line

`JAVA_HOME="/usr/lib/jvm/default-java"`

save file and refresh environment

`source /etc/environment`

You can check JAVA\_HOME enviroment variable by typing

`echo $JAVA_HOME`

and it will return path to java home as you just added to environment

`/usr/lib/jvm/default-java`

# Table of Contents

[1. Components installation](chapter1.md)

[2. MySQL installation](chapter2.md)

[3. Liferay installation](chapter3.md)

[4. Encrypting Tomcat Connections with Apache](#)

