---
title: 'Getting Ready to Learn MambaScript'
subTitle: 'How to setup your device for using mambascript'
excerpt: 'I want to be the best. I want to be the best simple and plain, thats what drives me - Kobe Bryant'
featureImage: '/img/mamba.gif'
date: '10/28/21'
---

<center>

# Getting Ready To Code In MambaScript

#### [Click Here To Go To Start-Here](/start-here)
#### [Click Here To Go To Getting Ready to Learn MambaScript](/learning-mambascript)
#### [Click Here To Go To Docs](/docs)

# Step 1

In order to use MambaScript you must have NodeJS installed on your machine, you can download NODEJS for Mac, Linux or Windows [__here__](https://nodejs.org/en/), make sure to choose the LTS version to download

[![nodejs](https://www.dropbox.com/s/ll8llnvjfce4zoh/Screen%20Shot%202021-10-31%20at%208.51.53%20PM.png?dl=1)](https://nodejs.org/en/)

# Step 2

After installing NodeJS you should now be able to open your Terminal Application and check to make sure you have properly installed it, open your terminal and type the following command (keep in mind you should not copy the $ , and if you may see a different symbol in your terminal at the beginning of every line  like maybe a %, as you will see if you follow me my terminal is customized and my symbol is a goat)
```bash
$ which node
```
![which node](https://www.dropbox.com/s/7o3gjyfjc6ep7ch/Screen%20Shot%202021-10-31%20at%208.59.31%20PM.png?dl=1)

as you can see the terminal responded to my `which node` command with the location of nodejs on my computer which
happens to be `/usr/local/bin/node`, the location of node on your machine doesn't need to match mine, but what's
important is your computer knows how where to access nodejs from.

# Step 3

Now we need to verify that you are using an up to date version of Node. we can do that by typing the following command

```bash
$ node --version
```
![node version](https://www.dropbox.com/s/oxcnvz19m9mjc1e/Screen%20Shot%202021-10-31%20at%209.03.51%20PM.png?dl=1)

As long as your node version is higher than 14.8 or higher you are good to go on Node


# Step 4

Now we need to install MambaScript globally on our machine with nodejs, this will allow us to be able to
execute `.mamba` files on our machine

```bash
$ sudo npm i -g mambascript
```
## or if you get a permission error try the below command to run the command as the root user

```bash
$ sudo npm i -g mambascript
```
Sudo stands for `super` `user` `do`. This keyword allows you to perform administrative tasks on your device. You will be prompted to enter your password when you do this. It's important to note 99% of the time this is your computer password
and also you won't see the password appear on your screen at all. This is for safety, just type the password and press enter/return.

# Step 5

Next you need to download the Atom Text Editor because it is the only editor that currently supports MambaScript,
soon we will support Sublime, Neovim and VS Code as well, and any other editor's will be up to the community to support.

You can download atom by clicking [__here__](https://atom.io)

[![atom](https://www.dropbox.com/s/jzwngsqjogj0q1o/Screen%20Shot%202021-10-31%20at%209.15.27%20PM.png?dl=1)](https://atom.io)

Note: If you are using a mac, make sure to drag and drop Atom into your Applications folder after you install it, if not you  will get weird bugs

# Step 6

Once you have opened Atom, you need to install the MambaScript Language package so you can now read MambaScript files.

![language](https://www.dropbox.com/s/ryw42jfzau5a1uf/Screen%20Shot%202021-10-31%20at%209.19.26%20PM.png?dl=1)

The one with the handsome black man next to it lol, is the one you want to install.


# Step 7

Pat yourself on the back your ready to start using mambascript on the machine you just set up.
# [Click Here To Go To Docs](/docs)


</center>
