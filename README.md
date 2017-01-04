# Liferay portal installation procedure on Ubuntu 16

## Introduction

This article will guide you through the step by step process of installing Liferay portal server boundled with Tomcat server and setup portal on Ubuntu server.

For storing data we will use MySQL server and this manual also corvers basic MySQL installation and basic security setup in order to work with Liferay.

For securing connection to the portal we will use Let's Encrypt SSL certificates.

SSL certificates are used within web servers to encrypt the traffic between the server and client, providing extra security for users accessing your application. Let's Encrypt provides an easy way to obtain and install trusted certificates for free.

We will also cover how to automate the certificate renewal process using a cron job.

## Prerequisites

* One Ubuntu 16 server \(tested on : 16.04, 16.10\)

Table of Contents
=================
[1. Components installation](chapter1.md) 

[2. MySQL installation](chapter2.md)

[3. Liferay installation](chapter3.md)

