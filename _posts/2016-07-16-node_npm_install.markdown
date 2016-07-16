---
layout: post
title:  "Note to Self: Installing Node and NPM when i'm not at home"
date:   2016-07-16 12:13:14 -0700
categories: NodeJS, MEAN_stack
---
**by Al Porotesano**

The simple path to building a Node app at Home where Home is my Linux Terminal (or Mac terminal or Windows Command Prompt / Powershell).

Start with the Terminal:

me@dingdong:~$ `the terminal syntax I should type`

1. `node -v`
2. `npm -v`
3. `express [name of project]`
4. `cd [name of project] && npm [name of project]`
5. `npm install -g express`
6. `npm install -g express-generator`
7. `ls`
	[displays list of modules and .js files on project]
8. `node app``
	*you should see:* Express server listening on port 3000 in development mode
9. `firefox`
	*test. dab. test. blah. done*
10. *Press Shift and C to exit localhost on terminal*


**Don't have Node or Node Version Manager?**

If you type nvm -v and nothing comes up, You'll have to install it. It's better to install it with the Terminal:

(I'm using Linux. Your Mac and Windows may vary)

1. `sudo apt-get update`
2. `sudo apt-get install build-essential checkinstall`
3. `sudo apt-get install libssl-dev`
4. `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh | bash`
5. `command -v nvm`
6. `nvm install 5.0`
7. `nvm use 5.0`
8. `nvm alias default node`

^^^ That method above is preferably easy to me. I can just use the Node package manager, use different versions of node and voila. I'm good to work.

Or maybe, i'm not necessarily thinking that's that easy. Maybe I do need Node.js after all.

So I'm on the node.js website to download the thing. I'm thinking, "ok, someone thought of us noobs with a simple download, right! I'm gonna download this zip thingy, unzip it, click install, and the computer is gonna do it all by itself for me."

Then I got moded. I thought wrong. I'm in a directory of links saying to myself "what the fuck is an x86?", "What psychopath thought we'd understand 32-bit or 64-bit as if we know how to drive the difference between a Ford Taurus or a Toyota Camry?"

You'll google for answers and you'll think one is right. Or not. You'll research for a million pages that have the same instructions:
	`sudo apt-get install nodejs`
and then you'll realize, "What version of node did I get?"

Before you turn into some dingdong banging your head to a wall or floor or sidewalk, Consider this easy approach for your workstation. Follow these steps.

1. `getconf LONG_BIT`
2. `uname -p`

If you use getconf `LONG_BIT`, you should have the bit version appropriate for the nodejs package to download (32 or 64 bit)

If you use `uname -p`, you should get the architecture version. x86_64 is 32-bit processors, AMD is for 64-bit processors. don't let the AMD name fool you if you're using Intel.

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

Sweet. Now I know i'm not a ding-dong.
