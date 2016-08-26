---
layout: post
title:  "Installing Drupal: Step 2 - Install & Configure MySQL database"
date:   2016-08-25 01:10:11 -0700
categories: Hackathon Homeless Drupal
---
**by Al Porotesano**

I have this post in mind for those of us in the homeless app project using drupal. So I'm going to assume you read step one, [if not go back to step one](http://nobleexperiment.github.io/hackathon/homeless/drupal/2016/08/24/Installing_Drupal_step1.html).

### Steps ###

	1. Install Apache & PHP
	>> 2. Install & Configure MySQL database <<
	3. Install & Configure SSL
	4. Configure the Apache VirtualHost
	5. Install & Configure Drupal 8

Let's revisit the requirements from the first step assuming you're using ubuntu 16.04

| *Requirement Settings*	|            |
|----------|:-------------:|
| *Storage* 	| 60 MB for Drupal |
| *Database*	| MySQL 5.5.3 or higher with PDO |
| *PHP* 		| 5.5.9 or higher |
| *Server* 		| apache |

As always type the mysql, apache2, and/or php --version on the terminal.

## 2. Install & Configure MySQL database ##

This one is fairly easy to set up. You're installing MySQL and configuring MySQL for Drupal.

I'll assume you're in root. If not and you forgot:

```sh
$ 	sudo su
```

*Install MySQL*

```sh
$ 	apt-get install mysql-server mysql-client -y
```

MySQL will ask you to create a new password. So go create one.

![mysql configuration](http://i.imgur.com/stjKaPV.png)

*Log in as Root*

```sh
$ 	mysql -u root -p
```

*You're in MySQL as Root, Now create a database for your drupal8*


```sh
mysql> 	create database drupaldb;
mysql> 	create user drupaluser@localhost identified by 'drupaluser@';
mysql> 	grant all privileges on drupaldb.* to drupaluser@localhost identified by 'drupaluser@';
mysql> 	flush privileges;
mysql> 	exit
```
Your terminal should look like my screenshot:

![step 2: granting your new drupal database privileges to your new drupal user before installing drupal.](http://i.imgur.com/uJA4qfE.png)

This completes Step #2

Step #3: Installing & Configuring SSL is next.

-al
