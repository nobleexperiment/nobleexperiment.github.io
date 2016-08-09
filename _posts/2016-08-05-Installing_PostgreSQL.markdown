---
layout: post
title:  "Installing PostgreSQL because other tutorials talk too much"
date:   2016-08-08 09:10:11 -0700
categories: Install_tutorial PostgreSQL
---
**by Al Porotesano**

[PostgreSQL](https://en.wikipedia.org/wiki/PostgreSQL) is an [object-relational database management system](https://en.wikipedia.org/wiki/Object-relational_database).

You could spend a week refreshing PostgreSQL stuff with tutorials and youtube videos and work on it for a bit, but one of my annoyances is reading postgreSQL install instructions that are too wordy that isn't understandably impressive.

This is one of those times where I'd like you to just read, type, and do by installing postgreSQL from your terminal. 

## Step 1. Add PostgreSQL apt repository ##

First, I add PostgreSQL repository in my system.

[Ubuntu includes PostgreSQL by default](https://www.postgresql.org/download/linux/ubuntu/). So that basically means you don't have to use the line apt-get install postgresql-9.4 anywhere in this tutorial. But, if you're using some other Linux distro like arch (on my older laptop, yes), you'd have to use that line later.

> $ sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" >> /etc/apt/sources.list.d/pgdg.list'
> $ wget -q https://www.postgresql.org/media/keys/ACCC4CF8.asc -O - | sudo apt-key add -

## Step 2. Install PostgreSQL ##

Second, Install the latest PostgreSQL server in my system using these commands.

> $ sudo apt-get update
> $ sudo apt-get install postgresql postgresql-contrib

## Step 3. Connect to PostgreSQL ##

Finally, we connect our postgres server and practice talking to it later.

> $ sudo su - postgres
> $ psql
> postgres-# conninfo

## step 4. Disconnect postgresql ##

> postgres-# \q
> postgres@linux:~$ *on your keyboard type* Control & D \* or apple-command & D if you roll on a mac \*
> postgres@linux:~$ logout

And that's a wrap. Unless you want to torture yourself at disconnecting postgresql like this:

quit()
quit
exit()
exit
q
q()
!q
^C
help
Alt + Tab
google.com
Quit PSQL
\q

Good luck talking to PostgreSQL. That's next.
