---
layout: post-classes
title:  "Project 1 Announcement"
date:   2016-09-21 19:57:57 +0900
author: Seongjin Lee
categories: project1 announcement
comments: true
---

## Objective

* Read part of kernel source code
* Understand what file systems do
* Peruse F2FS file system code


## Downloads

* Download Linux Kernel from following [link](https://www.kernel.org/pub/linux/kernel/v3.x/linux-3.18.1.tar.gz)
* untar the file with tar xvjf linux-3.18.1.tar.gz
* Install ctag. With Linux sudo apt install ctags ; with Mac, etags/ctags are shipped with the OS. You might want to upgrade the version by port install ctags

## What we will going to do in the class (Be prepared)

We are going to keep account of two information

* first one is how much write the file system receives
* second is how much does the file system actaully writes to the device
* Think about what kind of information you have to add and to where.
* If you are Mac user, you need to use a virtual machine to compile the kernel


## To Do

* read fs/f2fs/data.c
* read fs/f2fs/debug.c
* read other parts of the code, look for sb_info and see what kind of metadata a file system keeps
* search for any one of data structures, and try to figure out what it is


## Side notes you have to read

There are two files you have to read/understand and download before coming to the class. They are in [this link](https://github.com/resourceful/lecture_sysprog/tree/master/project1)

* How to compile the kernel
* How to use ctag accompanied with example codes
* codes are in [this link](https://github.com/resourceful/lecture_sysprog/tree/master/project1/codes)


## Due date
Learn by October 5, 2016

## If you are in trouble or need help

* Contact the TA


Highly recommend you to clone or fork  https://github.com/resourceful/lecture_sysprog and regularly pull for up-to-date materials.
