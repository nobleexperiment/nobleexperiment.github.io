---
layout: post
title:  "Installing Drupal: Step 1 - Check Prerequisites before Installing PHP & Apache"
date:   2016-08-24 09:10:11 -0700
categories: Hackathon Homeless Drupal
---
**by Al Porotesano**

I have this post in mind for those of us in the homeless app project using drupal. Let me tell you something: It's a bitch to install on my laptop.

I'm installing Drupal and watching this [Drupal Sites with Panthenon](https://drupalize.me/blog/201508/new-tutorials-manage-drupal-sites-pantheon) tutorial series thinking this will take all day.

I was going to post a series of questions with the whys and whats and whatever have yous, but it's just a paragraph full of ughs suitable for a livejournal post I doubt that would be worth reading. I just want to make the proceedures easier for the LBC uncoded hack against homeless team. Here's the breakdown of installations:

### Prerequisites ###

	1. 64-bit Ubuntu 16.04
	2. Terminal
	3. Root Privileges

### Requirements ###

We're focusing on Drupal 8 running MySQL. [Click here for System Requirements](https://www.drupal.org/docs/7/system-requirements/overview) to run previous versions of Drupal.

	1. *Storage* 	60 MB for Drupal
	2. *Database* 	MySQL 5.5.3 or higher with PDO
	3. *PHP* 	5.5.9 or higher
	4. *Server* 	Apache

To check if you have those versions on the terminal, type --version after mysql or php or apache.

### Steps ###

	1. Install Apache & PHP
	2. Install & Configure MySQL database
	3. Install & Configure SSL
	4. Configure the Apache VirtualHost
	5. Install & Configure Drupal 8

I know if I did these instructions again, It would take at least 3 hours. Give or take a few minutes working on some other project or facebooking something about something that something made about something when that something made some sense.

## 1. Install Apache & PHP ##

*Update the Ubuntu repository and install Apache:*

```sh
$ 	sudo su
$ 	apt-get update
$ 	apt-get install apache2 -y
```

*Install libapache for php7*

```sh
$ 	apt-get install libapache2-mod-php
```


*Install php7*

```sh
$ 	apt-get install php7.0 php7.0-fpm php7.0-mysql -y
```

*Enable Apache SSL and rewrite modules with the 'a2enmod' command. Restart apache to apply the changes:*

```sh
$ 	a2enmod rewrite ssl
$ 	systemctl restart apache2
```

*Check the modules are loaded with this line of command:*

```sh
$ 	apache2ctl -M | egrep 'ssl|rewrite'
```

The terminal should spit these out:

```sh
$ 	#Enabled
$ 	 rewrite_module (shared)
$ 	 ssl_module (shared)
```


If the above were shown on the terminal, mod-rewrite and mod-ssl are enabled and we're gonna continue on. If it's not, read the instructions on the terminal to install some mising component and re-check if your ubuntu enabled mod-rewrite & mod-ssl with: apache2ctl -M | egrep 'ssl|rewrite'.

*How do I know if Apache and PHP are working well?*

Let's create a new file in the **/var/www/html/** directory:

```sh
$	cd /var/www/html
$	echo "<?php phpinfo(); ?>" > info.php
```


*How do I test the info.php I just inserted?*

Use any browser and go **http://localhost:8080/info.php**
I'm using localhost for my laptop. You can use your AWS instance IP address or some IP addy your provider gave you, but i'm using localhost. 

*Final step:*

Remove info.php from the /var/www/html directory

```sh
$	rm -f /var/www/html/info.php
```

Step 2 will be Installing & Configuring the MySQL database. That's my next post tomorrow... It's gonna be a step per daily post thing.

- Al Porotesano
