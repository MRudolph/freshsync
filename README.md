freshsync
=========

This is a small program to one-way-syncing.
It copies files from one directory to another,handling the problem of limited disk space on the target.
This is useful for transferring podcasts on a mp3-player.

__Warning__: This means automatic deletion of files without asking for a confirmation. Don't use this for critical data.


While doing this, it handles the problem of limited diskspace in the target by following this rules:

* If there is space on the drive left, this will be used first
* If there isn't enough space for everything, only the newest files will be in the target directory
* To free space, the oldest files in the target will be deleted
* If they are too old, __even files only in the target will be deleted__, too
* Everything is handled on a file by file basis, so directories can be copied partially

Running with scala
------------------

This is a standalone script. Having scala installed you can run it via

    scala freshsync.scala <dir1> <dir2>
    
to copy files from dir1 to dir2. It will print out a detailled report on which files were present and what was done with each one.

Running with java
-----------------

I'm still looking for an easy way to bundle this up without the use of special build-tools, as this software has no dependencies except the scala runtime. Pull requests welcome.
