---
layout:     post-classes
title:      "Lecture 4"
description:   "Files and Directories "
date:       2016-09-26 23:51:00
author:     "Seongjin Lee"
comments: true
---
## Summary

This class deals with various APIs that manipulate files and directories.
We will learn more about stat structures, file attributes, briefly discuss file system structures and directory operations.

## List of topics

* stat and Related Functions
* Definition of the stat Structure
* File Types
* Let's improve the code (myls.c, Fig. 4.3)
* Set-User-ID and Set-Group-ID
* File Access Permissions
* access and faccessat Function
* access Function Example
* Order of Permission Tests
* umask Function
* umask Example
* umask More
* chmod, fchmod, and fchmodat Functions
* chmod Example
* chown, fchown, fchownat, and lchown Function
* File Size
* File Size Example
* File Truncation
* Disk drive, partitions, and a file system
* Cylinder group's inodes and data blocks in more detail
* Sample cylinder group after creating the directory testdir
* link(2) Function
* unlink(2) Function
* Open a file and then unlink it
* remove(2) Function
* rename Function
* Creating Symbolic Links
* Reading Symbolic Links
* File Times
* Effect of various functions on the \texttt{mac times}
* futimens, utimensat, and utimes Functions
* mkdir and mkdirat Functions
* rmdir Function
* Reading Directories
* Moving Around Directories


## Home works

* Review chapter 4
* Read chapter 5
  Setup ctag, download the kernel containing F2FS, we are going to implement new feature – more info at **[project announcement](http://resourceful.github.io/classes/2016-09-21-announcing-the-project/)**
