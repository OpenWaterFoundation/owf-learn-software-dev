# Development Environment Tools / Installer

Once software has been developed and tested, it must be packaged into a form that can be easily installed.
The installation package may be simple or involved depending on the complexity of the software,
the target operating system(s), and the target users.  Ideally, the installation should accomplish the following:

* let the user see what components are being installed
* install in a standard location by default, and possibly allow the location to be changed
* create entries in the system menu to start the software
* optionally create a shortcut on the desktop (if Windows)
* optionally add to the `PATH` environmental variable to allow finding the software name when typed in a command shell

Depending on the software, it may be appropriate to overwrite the previous version of the same software during installation.
or, it may be appropriate to install multiple versions of the software to allow transition and support different versions for compatibility
(for example Python has `python` and `python3` versions).

It is common to provide a program or script to start the software.

## Standard Software Installation Locations

Need to discuss here standard installation locations based on operating system and language platform.

## Windows:  Zip File

A simple install approach for Windows is to use a zip file, such as created by the [7zip](https://en.wikipedia.org/wiki/7-Zip) software.
Instructions should be provided describing where specifically the files should be installed.
This will not create a menu or desktop shortcut.

## Windows:  Installer

A more sophisticated approach is to create a software installer, for example using the [NSIS software](https://en.wikipedia.org/wiki/Nullsoft_Scriptable_Install_System).

Need to include more documentation.

## Linux:  tar.gz file

On Linux, software files can be packaged using the `tar` command.  For example use the following to create a tar.tz file and print filenames being processed:

```
$ tar -cvzf dist.tar.gz somefolder
```

## Linux:  Installer

Need to discuss `apt-get` and other approaches, depending on Linux distribution.
