---
layout: post
title:  "Mac下没有lsattr和chattr的替代方法"
categories: Mac
tags:  Mac shell
author: hjxfire
---

* content
{:toc}
今天在u盘里找到个上古病毒文件,有隐藏属性,在Mac下敲lsattr才发现Mac根本没这命令...后来网上找到了替代方法





## lsattr
可使用ls -lO 代替,注意是大写的O
```
    -O      Include the file flags in a long (-l) output.
```
效果:
```
$ ls -lO autorun.inf
-rwxrwxrwx  1 hjxfire  staff  uchg 54408  6  2  2008 autorun.inf
```
uchg就是该文件的隐藏属性

## chattr
可使用chflags 替代,想要删除A属性,只需要写chflags noA filename 即可  
效果:
```
$ chflags nouchg autorun.inf
$ ls -lO autorun.inf
-rwxrwxrwx  1 hjxfire  staff  - 54408  6  2  2008 autorun.inf
```
可以看见隐藏属性uchg已被删除.
<hr style="background-color: black;height: 1px;">
下面附上chflags的部分介绍:
```
NAME
     chflags -- change file flags

SYNOPSIS
     chflags [-fhv] [-R [-H | -L | -P]] flags file ...

DESCRIPTION
     The chflags utility modifies the file flags of the listed files as speci-
     fied by the flags operand.

     The options are as follows:

     -f      Do not display a diagnostic message if chflags could not modify
             the flags for file, nor modify the exit status to reflect such
             failures.

     -H      If the -R option is specified, symbolic links on the command line
             are followed.  (Symbolic links encountered in the tree traversal
             are not followed.)

     -h      If the file is a symbolic link, change the file flags of the link
             itself rather than the file to which it points.

     -L      If the -R option is specified, all symbolic links are followed.

     -P      If the -R option is specified, no symbolic links are followed.
             This is the default.

     -R      Change the file flags for the file hierarchies rooted in the
             files instead of just the files themselves.

     -v      Cause chflags to be verbose, showing filenames as the flags are
             modified.  If the -v option is specified more than once, the old
             and new flags of the file will also be printed, in octal nota-
             tion.

     The flags are specified as an octal number or a comma separated list of
     keywords.  The following keywords are currently defined:

           arch, archived
                   set the archived flag (super-user only)

           opaque  set the opaque flag (owner or super-user only).  [Directory
                   is opaque when viewed through a union mount]

           nodump  set the nodump flag (owner or super-user only)

           sappnd, sappend
                   set the system append-only flag (super-user only)

           schg, schange, simmutable
                   set the system immutable flag (super-user only)

           uappnd, uappend
                   set the user append-only flag (owner or super-user only)

           uchg, uchange, uimmutable
                   set the user immutable flag (owner or super-user only)

           hidden  set the hidden flag [Hide item from GUI]
```