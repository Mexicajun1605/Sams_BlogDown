---
date: "2023-08-18"
tags:
- Linux
- Computers
- Technology
title: Linux file system and Basic Terminal Navigation
---

# How does Linux work?

Linux is basically a series of files inside files inside files. Everything that you use to interact with the system can be found in the file system. These files are located in what are called folders. 

# Navigating files and folders
To navigate to a certain folder type the following code in the Terminal. You can access this on most distros by typing CTRL + ALT + T. 

```
$ cd /directory/subdirectory
```

Ignore the '$'; that just means you are in the terminal. 

Lets break that down. There is a lot going on here. cd stands for "change directory". Directory is just fancy Linux speech for folder. We divide the names of folders with the '/'. 
So you may ask why does it start with a '/'? '/' stands for the Root directory, or the basic level of the system where the most key permissions lie for file manipulation. We will get back to that in a second though. 
So in this instance above, 'directory' is a sub-directory  of the Root. 'subdirectory' is further more a sub-directory of 'directory'. Imagine it like those Russian nesting dolls. You have to open the top ones before going lower. 
However, unlike the Russian nesting dolls, you can use the 'cd' command to go anywhere in the system. Say there is a directory path, the series of directories and sub-directories, like the following '/usr/linuxpractice/hello/'. In order to access this directory, you can merely type it from anywhere in the system, provided you have root permissions, and get there. 

```
$ cd /user/linuxpractice/hello/
```
Now back to the Root. The root can instantly be accessed by typing a mere '/' after cd. It is from here that we are going to explore the main directories, 
bin, boot, etc, home, tmp, and var. There is a lot more to what is going on in the Root directory, but we can worry about those in another post. Furthermore, root users are marked by a '#' after their names in the terminal. To access the root permissions use the following commands and be prepared with your root password, which should have been setup on your Linux install. 

```
$ sudo -s
```

Once in the Root directory we use the ls command to see everything. I like to think of it as meaning list. Once you have done that it should look like the example below. 

```
$ ls
bin    dev   lib    libx32      mnt   root  snap      sys   usr
boot   etc   lib32  lost+found  opt   run   srv       test  var
cdrom  home  lib64  media       proc  sbin  swapfile  tmp
```

# bin 

bin is short for Binary. Here is where a lot of the programs that you usse here in the terminal live. Go ahead and navigate to the bin directory and use the 'cd' command to locate the 'ls' command.

Interestingly if you open up some of the files in this directory, you will notice that you only have gibberish. This is because they are written in binary. If you would like to try it out, use the 'nano' command followed by the program or file of interest. For example, to see the contents of the 'ls' command, type the following. 

```
$ nano ls 
```

# etc 

The etc, pronounced 'etsy', directory contains configuration and networking files. To get here, wer are going to use a variation of the 'cd' command that will allow us to move up exactly one directory. 

``` 
$ cd ..
```

By writing this command you are telling the terminal to move you up exactly one directory, so by using this command we are leaving 'bin' and moving into the root. From here just 'cd' into the 'etc' directory. 

As previously said, this directory is where the configuration and networking files on the linux system live. While scrolling through the available files here, we can find things like 'network', 'netplan', and 'NetworkManager'. We can also find a folder for 'systemd' programs. 'systemd' is what allows you to do a lot of the basic things on the system such as user management processing. 
# dev 

Next up, we have the dev directory. You might think that this is short for developer, but rather it stands for devices. This is where the devices on your system live. For example, your hard drive can be found here. On my system the hard drive is listed as 'ssd1' however, you might find your drive listed as 'hdd1' or something else similar. 

# lib 

There are several of these, but they all tend to share the same purpose. This directory contains libraries of code that other programs use. Think of it like the Google for the file system. When the system does not know what to do, it goes and looks here for the answer on how to do something. 

# home 

This directory is where the system user information lives. For example, if a system has two users named 'Bob' and 'Alice', there information will be stored in the home directory, each as sub-directories. From here, you can navegate, if you have the correct root permissions, into any user directory. 

To acquire root permissions/access, type the following command below. It should show your user followed by the '#' symbol. You will have to know the root password to do this though. 

```
$ sudo -s
```

# tmp

This is where the temporary files on the system live. Think of it kind of like the cache on the web browser. Once the cache is cleared, or if you have your browser set to clear the cache upon close, the cache is empty. The tmp directory, however, clears upon reboot or shutdown. 

# var

Finally we have reached the last directory that we are going to talk about, var. Here is where 'variable' programs and commands are stored. You can even store a web server and website here! To do that, you just have to create a directory in the var folder called 'www'. To make a directory in the terminal we use the 'mkdir' command. The abbreviation should be obvious. 

```
$ mkdir www
```

After that directory has been made, you can make another 'html' directory. Within the 'html' directory, create another directory with the desired name. Here we are going to make something super simple with the following commands. 

```
$ mkdir html
mkdir helloworld
nano helloworld.html
```

Once you have opened the helloworld.html, simply type whatever you want in the file and navigate to the following url in any web browser. http://localhost/helloworld/helloworld.html 

Voila! You just made a web server! Note that you need to have web server software installed in order for this to work, such as Apache. However, many major Linux distros will come with apache preinstalled. 

To remove this dummy directory we use the 'rm' and the 'rmdir' commands to remove files and directories respectively. Use the following inside the helloworld directory to get rid of these. 

```
$ rm helloworld.html
cd ..
rmdir helloworld
```

# Conclusion 

And there you have it! The Linux file system in a nutshell. There is a lot more here that I did not cover, however, this should cover a lot of what you might need to know about as what I would consider a regular user. 