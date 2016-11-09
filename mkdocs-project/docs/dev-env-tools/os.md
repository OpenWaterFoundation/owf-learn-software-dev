# Software Development Environment / Operating System

The operating system is the software that interacts with hardware devices to provide the working environment
for basic functions (saving files to hard disk, printing, networking, etc.) and provides a platform for other software.

## Operating System Types

Examples of operating systems are listed below.
It is common to refer to the operator system when describing the computer, such as "Are you using a Windows 7 computer?"

* [Microsoft Windows 7](https://en.wikipedia.org/wiki/Windows_7)
* [Microsoft Windows 10](https://en.wikipedia.org/wiki/Windows_10)
* [Mac OS X](https://en.wikipedia.org/wiki/MacOS)
* [iOS](https://en.wikipedia.org/wiki/IOS)
* [Linux](https://en.wikipedia.org/wiki/Linux)
* [Android](https://en.wikipedia.org/wiki/Android_(operating_system))
* [Cygwin](https://en.wikipedia.org/wiki/Cygwin)

The above operating systems indicate variability in business models and ownership of intellectual property.
For example, Microsoft operating systems are proprietary software that must be licensed from Microsoft.
The OS X and iOS operating systems must be licensed from Apple.

Linux is an open source operating system that runs on many types of devices.
There are many variations of Linux, typically focusing on the size of the operating system, performance,
number of supported hardware components, supported software, etc.
These variations of Linux are called [Linux distributions](https://en.wikipedia.org/wiki/Linux_distribution).
Many organizations, including nonprofits, for-profits, and virtual organizations, have been formed to develop and maintain Linux distributions.

Android is a variation of Linux developed by Google to serve as the operating system of smart phones and devices such as smart TVs.

Cygwin is a Linux-like operating system that runs on top of Windows.  After installing, many Linux programs (compiled for Cygwin) can be run in a Cygwin terminal and Windows files
and programs are also accessible.  This provides a compromise solution but it does have limitations.
In particular, Cygwin may be useful for desktop use and development, but it is not generally suitable for a server (instead, use Linux or a virtual machine).
Cygwin may be a good solution when taking the leap of using virtual machines is too big of a leap.

The operating system decision is also impacted by whether 32-bit, 64-bit, or other architecture are used.
Many operating systems are moving towards 64-bit versions because of hardware changes.
Software developers must understand whether 32-bit or 64-bit versions of software are required for distribution,
although this is less of an issue for interpreted languages that are not compiled into executables (see the [Compiler section](../dev-env-tools/compiler/)).

There has been a general trend towards running operating systems on different types of devices (desktop computers and laptops, tablets, and smart phones).
However, the requirements of each device has limited full portability.

Software developers must decide which operating system(s) to support, which impacts choices in programming language and software tools.

## Virtual Machines

A [virtual machine (VM)](https://en.wikipedia.org/wiki/Virtual_machine) is a virtual (guest) operating system that runs on top of the host operating system.
This allows software to be developed and run in a controlled operating system environment.
The guest VM must be configured to properly utilize the host computer's resources, such as hard drive, USB drives, mouse, display, and network.

Multiple VMs can run on one computer, thereby reducing costs because fewer computers need to be purchased.
The software that provides VM functionality must be installed on the host operating system before guest operating system VMs can be created.
Examples of common virtual machine software include:

* [Virtual Box](https://en.wikipedia.org/wiki/VirtualBox), which is open source and supported by Oracle
* [VMWare](https://en.wikipedia.org/wiki/VMware_Workstation), provided by VMWare 
* [Hyper-V](https://en.wikipedia.org/wiki/Hyper-V), which is provided by Microsoft

Resources are required to install and configure VMs.  However, once the initial investment in learning is made, it is easy to scale VMs to nearly any task.
Note that virtual machines may have a cost.  For example, Microsoft and Mac operating systems are not free to install, whereas Linux is often free.

## Operating System Update Management

Each operating system (as well as many platforms) typically provides software to manage updates.
This is required because the large number of software programs on a computer must be updated consistently to prevent conflicts in underlying libraries and dependencies.
A software registry/catalog/package list/repository is maintained by the update software, which can be updated from the internet,
and allows software installations and updates to be requested.  The following are examples of software update tools:

* Windows:  [Windows Update](https://en.wikipedia.org/wiki/Windows_Update) (mainly for the core operating system and Microsoft software)
* Linux:  [Advanced Packaging Tool (apt)](https://en.wikipedia.org/wiki/Advanced_Packaging_Tool), used by some Linux distributions,
and each distribution uses something similar
* Python language:  [package manager (pip)](https://en.wikipedia.org/wiki/Pip_(package_manager)), used to install Python packages

Note that some of the above examples are for operating systems and some are for software languages.
These tools will be discussed more in other sections of this documentation.

## File Separator Differences

The file separator is the character between folders and filenames:

* Windows:  \
* Linux-like:  /

Windows also introduces drive letters such as `C:` in front of file paths.
Software should be written to handle input generally so that the software can run on any operating system.

## Path Separator Differences

The path separator is the character used to separate folder (directory) names in the `PATH` environment variable.
The `PATH` environment variable is used to indicate folders to search for programs to run, when a program name is run in a command shell.
The following path separator character is used on various operating systems:

* Windows:  `;` (semi-colon)
* Linux-like:  `:` (colon)

## Text File End of Line Differences

Operating systems differ in how they represent the [end of line (newline)](https://en.wikipedia.org/wiki/Newline) in text files:

* Windows:  CR+LF (carriage return and linefeed)
* Linux-like:  LF (linefeed)

These are hidden characters that are not typically seen in text editors.

Differences in the end of line representation can result in issues when trying to write software that works on any system.
In general, software should handle either case, for example:

* when writing files, write the end of line character(s) appropriate for the operating system
* when reading files, handle end of line character(s) from any operating system
* be consistent in a file - write one or the other but don't mix

The end of line character can complication [version control](../dev-env-tools/version-control/) because multiple software developers
using different operating systems for the development environment can introduce different line endings.
There are conventions to minimize these issues, as described in the version control section.

## Command Shell

A basic interface to an operating system is the command shell,
which is a program that runs programs given the program name and command line parameters.
Although operating systems support programs with graphical user interfaces,
it is often necessary as a software developer to install and run programs using a command shell.
Command shells are discussed throughout this documentation.  Examples of command shells are:

* Windows 7, 10:  `cmd.exe`
* Linux, Cygwin:  `bash`

## Runtime Environments

Software is written for one or more operating systems, typically using standard libraries that interface to the operating system.
It is often possible to write software that will run on multiple operating systems,
although there are complications because of limitations in support for underlying software libraries,
and, in particular, graphical user interface environments.
It is desirable to write software that will run on multiple operating systems.
However, this may not be practical and decisions will need to be made to ensure meeting basic requirements first.

Software may also be written to run in a *runtime environment*, which provides an additional layer of functionality and specifications.
The Java language was developed in part to ["write once run anywhere"](https://en.wikipedia.org/wiki/Write_once,_run_anywhere),
meaning that the software can run on any operating system.
This is accomplished in a runtime environment because the runtime environment does the work of
wrapping the operating system to provide a standard software environment across operating systems.

See the [documentation discussing runtime environments](../dev-env-tools/runtime-env/) for background.
