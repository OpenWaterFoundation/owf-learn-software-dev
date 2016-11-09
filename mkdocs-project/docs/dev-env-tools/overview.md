# Software Development Tools Overview

Software development tools are the tools of the trade for software developers,
and will vary depending on the programming language and target operating system:

* Operating System - Windows, Linux, Cygwin, Mac OS X, virtual machines, etc. that provides core computer platform
* Compiler - software that converts source code into executable programs (only needed for some languages)
* Text Editor - software that edits text files such as code and configuration files
* Interactive Developer Environment (IDE) - software that provides an integrated graphical user interface for software development
* Runtime Environment - a runtime environment ("virtual machine" or interpreter that runs the software in the operating system),
used by some languages like Java and .NET
* Version control - tools that track changes in files to facilitate finding bugs and versioning software
* Debugger - software that helps inspect running programs for variable contents, etc.
* Documentation - standards and software that creates developer documentation
* Logging Framework - software that manages messages generated in the target software, useful for troubleshooting
* Test Framework - software that allows the target software to be tested
* Installer - packaging the software for installation on the target operating system

Some of the tools (such as compiler) are only used during software development and others
(such as operating system and installer) reach back into the operating system
and must be considered during developer environment setup and deployment of the software.

The following sections describe approaches in configuring a software development environment.
The selected approach will be defined by the software development project, its team, and technological constraints.

## Location of Development Environment Tools on Computer - Distributed Environment

A software developer environment that is distributed on a computer typically means that some components are re-used between
software projects.  For example, software compiler, editor, version control software, etc. are installed in standard software locations:

* Linux:  `/opt`, or `/usr`, for example
* Windows:  `C:\Program Files` or `C:\Program Files (x86)`

The software is reused between software projects and typically does not change from project to project.
Different versions of software, such as compilers, may be installed.

Some tools, such as Eclipse integrated developer environment (IDE) uses a workspace folder to customize the development environment tools.
This folder contains plugin files, such as configuration and temporary files.

Software projects typically use one or more version control repositories (each in a folder),
which contain source code, documentation, tests, and other files related to the software.
These are the only files saved in a version control system - the software files and Eclipse workspace are not saved in a repository.

| OS     | Shared Software Install Folder | Workspace Folder (IDEs like Eclipse) | Software Project Files (repository folder) |
| ------ | --------------------- | ------------------------------------ | ------------------------------------------ |
| Linux  | `/opt` or `/usr`, for example | `/home/someUser/someWorkspace` | `/home/someUser/someRepo` |
| Windows| `C:\Program Files`, `C:\Program Filex (x86)`,  or `C:\SomeSoftware` | `C:\Users\someUser\someWorkspace` or `C:\someWorkspace` | `C:\Users\someUser\someRepo` |

The above approach requires that the software developer understand the locations of different components on the computer,
for use in the software project.  The advantages of this approach are:

* Software is installed once and shared between software projects, so less disk space is used and less installation time
* Some software only allows one installation on the computer, consistent with this approach
(and does not support the approach in next section)
* Shared software on a shared computer may introduce issues when used by multiple software developers
* Version control repository folders are shared between software projects (can also be a disadvantage).

The disadvantages of this approach are:

* It may take more time to install software components and administrator privileges may be needed.
* Because software tools are shared, there may be more confusion about what is used for any software project.
* There is less control within a project over what software is used by the project;
however, this can be controlled through configuration, scripts to run tools, etc.

## Location of Development Environment Tools on Computer - Packaged Environment

Another approach is to install all or most software for the developer environment in a packaged, environment.
This is sometimes called a virtual environment, or appliance.
In this approach, the software developer project consists of all or most necessary software installed under a folder.

One example is the
[Python `virtualenv` tool](https://virtualenv.pypa.io/en/stable/) for Python language projects.

Another example of this approach is an Eclipse software project on Linux-like operating system, where the Eclipse IDE,
Java SDK and JRE, Eclipse workspace, and Git repository containing software project source files are installed in a folder in the
software developer's home folder.
Or, taken to an extreme, a virtual machine can be dedicated to development of one software project (probably too much work).

| OS     | Example Umbrella Folder         | Eclipse Install Folder | Workspace Folder (IDEs like Eclipse) | Software Project Files (repository folder) |
| ------ | ------------------------------- | ----------------------- | ------------------------------------ | ------------------------------------------ |
| Linux  | `/home/someUser/umbrellaFolder` | `umbrellaFolder/eclipse` | `umbrellaFolder/someWorkspace` | `umbrellaFolder/someRepo` |
| Windows| `C:\Users\someUser\umbrellaFolder` or `C:\umbrellaFolder` | `umbrellaFolder\eclipse` | `umbrellaFolder\someWorkspace` | `umbrellaFolder\someRepo` |

The advantages of this approach are:

* All (or most) software for the software development project are included under an umbrella folder,
so it is more obvious what tools are used.
In the table above only Eclipse is installed under the umbrella but other software could be installed, such as Java compiler (or Python software if using Python).
* Installation in the developer's folder does not require administrator privileges.
* Configuration of software for the specific software project is not impacted by other software projects.

The disadvantages of this approach are:

* More disk space is used because software is installed multiple times (once for each virtual environment),
in particular if different versions of the software need to be installed and tested.
* More time is required to set up redundant environments, although a setup script can be created to install and configure the software tools in a standard way.
* Some software tools may not allow installation of multiple copies.
* Multiple copies of shared version control repositories (such as Git repositories) need to be created (one in each virtual environment) and there is extra effort to keep synchronized.
* Complex development environments may require using different versions of developer tools such as Python 2 and 3, Java versions, etc.
This may also cause the packaged approach to be adjusted to the distributed approach.

## Location of Development Environment Tools on Computer - Hybrid Environment

A hybrid approach for development environment file locations is to use symbolic links within the umbrella folder described in the previous section,
to share software locations, repositories, etc. between packaged software development environments.
However, this begins to shift the concept of the packaged approach to look like the distributed developer environment described in the first approach.

Ultimately, it may be up to the individual developer as to what they prefer.
Because the repository only contains source code, and not software tools, care should be taken to configure files in the repository to work
independent of the software developer's environment configuration.
