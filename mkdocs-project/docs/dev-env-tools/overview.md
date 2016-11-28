# Development Environment Tools / Overview

Software development tools are the tools of the trade for software developers,
and will vary depending on the programming language and target operating system.
The following tools are listed in approximate order of dependency and use.

* **Operating System** - Windows, Cygwin, Linux, Mac OS X, either on a physical machine or run through a virtual machine, that provides the core computer platform
* **Version control** - tools that track changes in files to facilitate new development, finding bugs, and versioning software
* **Compiler** - software that converts source code into executable programs (only needed for some languages)
* **Interpreter** - software that reads source code and executes it without compiling (only needed for some languages)
* **Text Editor** - software that edits text files such as code and configuration files
* **Difference Tool** - software that shows the difference between files
* **Interactive Developer Environment (IDE)** - software that provides an integrated graphical user interface for software development
* **Runtime Environment** - a runtime environment ("virtual machine" or interpreter that runs the software in the operating system),
used by some languages like Java and .NET
* **Debugger** - software that helps inspect running programs for variable contents, etc.
* **Documentation** - standards and software that creates developer documentation
* **Logging Framework** - software that manages messages generated in the target software, useful for troubleshooting
* **Test Framework** - software that tests the target software in a controlled and automated way, to consistently validate software against benchmarks
* **Installer** - packaging the software for installation on the target operating system

Some of the tools (such as compiler) are only used during software development and others
(such as operating system and installer) reach back into the operating system
and must be considered during developer environment setup and deployment of the software.

The following sections describe approaches for installing software tools so that they are accessible to a software development project.
It is assumed that the software developer uses a dedicated development space, such as:

* Personal file space:
	* Linux & Cygwin:  `/home/someUser`
	* Windows:  `C:\Users\someUser`
* Shared space on dedicated computer:
	* Linux & Cygwin:  there is typically no reason to develop outside of a user's file space.
	It is typical to test in deployed system folders.
	* Windows:  Use of `C:\someFolder` will generally not interfere with other users.
	It is typical to test in deployed system folders.

The selected approach for installing each software tool depends on the needs of the software development project,
its team, target deployed system, and other technological constraints.
A [project-based development files structure](../overview#software-project-file-organization) is recommended.

Software tools are generally installed in one of three locations, which are each discussed in more detail in the following sections:

* Install on the operating system in standard location - typically the default location when a software installer is run.
* Install on the operating system in a custom location - for example, if not an official release on the operating system.
* Install in the development files - provides the most control for developers

A software development project often uses software tools installed in multiple locations.

## Install Development Tools in Standard Location on Operating System

It is often appropriate to install software development tools in standard locations on the operating system,
in particular when the tools do not need to be changed after installation.
Software installed in the default operating system location often requires administrator privileges (root on Linux)
and once installed is intended to remain unchanged until an update is installed.

The advantages of this approach are:

* Software is installed once and shared between software projects; therefor, less disk space is used and less time for installation

The disadvantages of this approach are:

* Some software only allows one installation on the computer, which can be problematic if different software projects
require different versions of software; however, many development tools allow installation in a versioned folder
* Shared software on a shared computer may introduce issues when used by multiple software developers;
however, most development environments such as IDEs store separate files to avoid these issues
* It may take more time to install software components and administrator privileges may be needed;
however, most tools have easy to use software install processes
* Because software tools are shared, there may be more confusion about what is used for any software project - this can
be overcome by using a script to run the proper version
* There is less control within a project over what software is used by the project;
however, this can be controlled through configuration, scripts to run tools, etc.

### Linux

Linux distributions are often managed with tools like `apt-get`, which simplifies installing software and dependencies.
Software tools can be researched to determine whether a needed version is available on the target operating system.
For example, see the following page for information about installing Java for
Debian Linux:  [https://wiki.debian.org/Java/](https://wiki.debian.org/Java/).

The software will be installed in standard location(s) on the operating system.
The latest installation that is run may reset the default to that version, for example because of symbolic links created in `/usr/bin`.
However, it is often possible to run a specific version by determining the location where files are actually installed
and bypassing the default symbolic link.

### Cygwin

[Cygwin](https://cygwin.com/index.html) uses its own installation manager.
Software selected to install typically installs the latest version,
although some software includes the version number and manual installation of tools can occur,
separately from the Cygwin installer.

### Windows

Most software programs have defaults that install into `C:\Program Files` (64-bit), `C:\Program Files (x86)` (32-bit), or
another location (e.g., Python installs into `C:\Python27` or `C:\Python35`).

## Install Development Tools in Custom Location on Operating System

It may be appropriate to install software in a custom location on the operating system,
for example in the case where a standard installer is not available and/or it is desirable to install a version
separately from the latest official release.

The path to the software executable may not be automatically added to the `PATH` environment
variable and therefor running the software may require a script or selecting the executable by full path.

### Linux and Cygwin

A typical custom installation location is `/opt`.
Such installs are typically done as the root user and cannot be updated by a normal user.

### Windows

Similar to Python, it may be appropriate to install software in `C:\SomeFolder`.

## Install Development Tools in Development Files

It may be desirable or necessary to install a development tool in the development files.
If following the [general template file structure](../overview#software-project-file-organization),
software would be installed under `$HOME/org-dev/ProjectName/tools`, with a separate folder
for each software tool.  This ensures that the software is independent of operating system versions.
Such installs can typically occur using the user account rather than administrator,
and allow full control over the software.
As such, this approach may be appropriate if administrator privileges are not available on the computer.

The advantages of this approach are:

* Software for the software development project is included under an umbrella folder,
so it is more obvious what tools are used.
* Installation in the developer's folder does not require administrator privileges.
* Configuration of software for the specific software project is not impacted by other software projects.

The disadvantages of this approach are:

* More disk space is used because software is installed multiple times (once for each development project),
in particular if different versions of the software need to be installed and tested.
* More time is required to set up redundant environments, although a setup script can be created to install and configure the software tools in a standard way.
* Some software tools may not allow installation of multiple copies.
