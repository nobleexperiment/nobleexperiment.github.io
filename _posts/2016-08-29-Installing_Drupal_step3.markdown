---
layout: post
title:  "Installing Drupal: Step 3 - Install & Configure SSL"
date:   2016-08-29 09:10:11 -0700
categories: Hackathon Homeless Drupal
---
**by Al Porotesano**

I have this post in mind for those of us in the homeless app project using drupal. The first two steps are linked in the table of contents aka steps:

| 		|  Steps |
|:----------|-------------:|
| *1*	| [Install Apache & PHP](http://nobleexperiment.github.io/hackathon/homeless/drupal/2016/08/24/Installing_Drupal_step1.html) |
| *2*	| [Install & Configure MySQL database](http://nobleexperiment.github.io/hackathon/homeless/drupal/2016/08/25/Installing_Drupal_step2.html) |
| *3*	| >> *Install & Configure SSL* << |
| *4*	| Configure the Apache VirtualHost |
| *5*	| Install & Configure Drupal 8 |

We'll need SSL to ensure secure access to Drupal. Let's do so with these simple steps:

You'll need to be a superuser. If you forgot:

```sh
$ 	sudo su
```

1. Create a new SSL folder in the Apache configuration directory. This will allow storage of the SSL certificate we're going to create in steps 2 & 3:

```sh
$ 	cd /etc/apache2/
$ 	mkdir ssl
$ 	cd ssl/
```

2. Create a self-signed certificate:

```sh
$ 	openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/drupalssl.key -out /etc/apache2/ssl/drupalssl.crt
```

3. Change the permission of the certificate file:

```sh
$ 	chmod 600 *
```

Achievement Unlocked: You created an SSL Certificate file for securing Drupal.

Step 4: Configure the Apache VirtualHost

- Al
