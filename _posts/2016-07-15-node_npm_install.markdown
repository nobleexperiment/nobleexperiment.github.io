---
layout: post
title:  "Note to Self: Installing Node and NPM when i'm not at home"
date:   2016-07-15 12:13:14 -0700
categories: MEANstack EasyPeasy
---
**by Al Porotesano**

The simple path to building a Node app at Home where Home is my Linux Terminal (or Mac terminal or Windows Command Prompt / Powershell).

Start with the Terminal:

me@dingdong:~$ `the terminal syntax I should type`

##NVM or Node? You can do both, but it's a headache

Yeah I could install both NVM and Nodejs, but it's a headache to even try. If I install NVM, I can go to [nodejs.org](https://www.nodejs.org) and see the stable version to work with. If I install nodejs, I'm just going to use the current version and forget I'll have to update it later. Or maybe I can be content with the current version until it's out of fashion.

**Installing NVM**

If you type nvm -v and nothing comes up, You'll have to install it. It's better to install it with the Terminal:

(I'm using Linux. Your Mac and Windows may vary)

1. `sudo apt-get update`
2. `sudo apt-get install build-essential checkinstall`
3. `sudo apt-get install libssl-dev`
4. `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh | bash`
	*restart terminal to boot nvm*
5. `command -v nvm`
6. `nvm ls-remote`
6. `nvm install 4.4.7`
7. `nvm use 4.4.7`
8. `nvm alias default node`

*note: 4.4.7 is the current stable version when I wrote it on July 15, 2016*

I guess that was easy. I can just use the Node Version Manager, choose a version, and I'm good to go.

Maybe it's necessary to use `sudo apt autoremove` if my terminal says so after I `sudo apt-get install libssl-dev` to get rid of the useless libs in my machine.

Or maybe, I'm not necessarily thinking it's that easy. 

Maybe I do need to just install Node.js after all.

**Installing Node.js**

I'm on [nodejs.org](https://www.nodejs.org) to download this thing thinking, "ok, someone thought of us noobs with a simple download, right! I'm gonna download this file, click install, and the computer is gonna do it all by itself for me."

Then I got moded. I thought wrong. I'm in a directory of links saying to myself "what the fuck is an x86?", "What psychopath thought we'd understand 32-bit or 64-bit as if we know how to drive the difference between a Ford Taurus or a Toyota Camry?"

You'll google for answers and you'll think one is right. Or not. You'll research for a million pages that have the same instructions:
	`sudo apt-get install nodejs`
and then you'll realize, "What version of node did I get?"

Before you turn into some dingdong banging your head to a wall or floor or sidewalk, Consider this easy approach for your workstation. Follow these steps.

1. `getconf LONG_BIT`
2. `uname -p`

If you use getconf `LONG_BIT`, you should have the bit version appropriate for the nodejs package to download (32 or 64 bit)

If you use `uname -p`, you should get the architecture version. x86_64 is for 64-bit processors. xi86 is for 32-bit processors. I know the 64-bit has more stuff to do.

Still in Terminal?

1. `firefox`
	1. http://www.nodejs.org
	2. click the left green button that has the words "Recommended for most users" above the version number.
	3. save it on your Download folder (People smarter than me know they can download it anywhere)
2. `cd Download`
3. `ls Download`
	1. list of files in Download folder should show *node-v4.4.7-linux-x86.tar.xz* (latest version when I was writing this in July 2016)
4. `sudo apt-get install xz-utils`
5. `tar -C /usr/local --strip-components l -xjf node-v4.4.7-linux-x86.tar.xz`
6. `ls -l /usr/local/bin/node`
7. `ls -l /usr/local/bin/npm`

instructions no. 6 and no. 7 should tell me I have both node and npm in my bin folders.

**Installing NVM or Nodejs or both is fine. I prefer NVM for backward and forward compatibility of my stuff**

Sweet. Now I know i'm not a ding-dong.

##Now to my node project

Follow the steps if this is your first time:

1. `node -v`
2. `npm -v`
3. `sudo apt install node-express-generator`
3. `express [name of project]`
4. `cd [name of project] && npm [name of project]`
5. `npm install -g express`
6. `npm install -g express-generator`
7. `ls`
	[displays list of modules and .js files on project]
8. `node app`
	*you should see:* 
	Express server listening on port 3000 in development mode
9. `firefox`
	*test. dab. test. blah. done*
10. *Press Shift and C to exit localhost on terminal*

If you're going to do this continouously:

1. `express [name of project]`
2. `cd [name of project] && npm [name of project]`
3. `npm install -g express`
4. `npm install -g express-generator`
5. `node app`
6. `firefox`

Not sure what IDE app you use to write your project, but Sublime text is great because it's free and i'm poor.

- Al Porotesano

