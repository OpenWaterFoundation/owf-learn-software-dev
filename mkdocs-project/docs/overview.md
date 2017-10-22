# Overview of Software Development #

A software development project requires a level of effort along a spectrum,
depending on the required skills and technologies, and distribution of the software.
The term "project" is used to indicate work done to develop software.
The term "product" is used when a software program/tool/system is created with clear identity and purpose.
The software project is used to create the product.

On the simpler side is a one-off simple tool created to do a job for one person, that will never be used again...throw-away code.
A common example is creating a script to perform data processing steps - the script memorializes the analysis steps so that it is
easy to see later the steps that were performed.
Even development of simple tools may involve using powerful software tools and can implement best practices used in more complex projects.
At a minimum, one-time tools should be managed in a way that allows them to be reused later.
For example, save the software tool with project files and create minimal documentation.

On the other extreme is a full software project involving licensing, development environment standards, versioning,
documentation, distribution, support, maintenance, etc.
These software projects may involve teams of multiple developers,
including open source projects with potential to involve collaborators on the web.
Complex projects require the establishment of guidelines so that the development effort is efficient.

This documentation will not delve into all aspects of the latter case but will provide a template that can be adapted for multiple projects.
Many aspects of any software project are covered in
["Producing Open Source Software - How to Run a Successful Free Software Project"](http://producingoss.com).

This documentation focuses on technical aspects that can be found in any major software project,
in particular topics relevant to the Open Water Foundation and development of software for water resources:

* Development environment tools
* Software development environment setup
* Software development tasks

These topics will vary greatly depending on the chosen programming language and target operating system and computer devices.
However, many concepts are the same or similar and are covered in this documentation.

## Software Project File Organization ##

It is beneficial to organize software project files in a consistent way that recognizes common file content and work tasks.
Every software developer has their own preferences for how to organize a software project;
however, the reality is that many software projects are so complex that a standard development environment should be followed.
Otherwise, it is difficult to develop standard documentation for developers and troubleshooting becomes more difficult.
A standard file organization is particularly important for complex software projects with many components.

It is helpful for software developers to work on multiple projects with multiple teams in order to learn
what works, and to infuse best practices in software projects that can be improved.
It is also helpful for software developers to recognize that there is no one approach that will work for all software projects,
and an open mind is needed.

The following are guidelines for software development project file organization:

* Understand the core files that comprise a software product, and manage those resources in version control.
* Build in documentation from the start, in code comments, developer documentation, and user documentation.
* Describe how to set up a standard development environment, so that there is a working example - this will minimize
frustration in cases where the development environment is complex and there are many places where something can break.

The following is an example file structure that applies to many software projects,
and will be referred to as "development files".
All files in repositories are managed in the cloud - in the following example Git is used for repositories.
All other files will need to be set up by the developer, although scripts may be provided to facilitate setup.
Often setup involves creating top-level development folders and then checking out one or more Git repositories
so that developer documentation can be reviewed locally, to help complete setup of the development environment.

```text
$HOME/                                   (Developer's home folder /home/user on Linux/Cygwin, and C:/Users/user on Windows.)
  org-dev                                (Top-level folder indicating where development projects will live, where
                                          "org" indicates the organization associated with the project.
                                          This allows a person to work on development for multiple organizations, with some
                                          sense of who the software project.)
    projectName1/                        (Folder containing project development files.
                                          The name of the project should be clear, for example ProductName.)
      bin/                               (Folder containing scripts such as start-up script for IDE,
        scripts, etc.
                                          to ensure that proper development software versions are used.)
      xxx-workspace/                     (Folder used by IDE workspace, when not appropriate for in Git repository.
                                          For example, the Eclipse IDE creates a .metadata folder under the workspace folder that
                                          is not generally suitable for storage in the repository because dynamic
                                          files will vary by developer.)
      git-repos/                         (Git repositories that contain files used in the software project.  Run the following here:
        repo-1-name/                      git clone https://pathToRepo.git
        repo-2-name/                      where the path to the repository is provided by GitHub, Bitbucket, etc.)
          README.md                      (Standard repository readme Markdown file explaining content and setup.)
          .gitignore                     (Git configuration file to ignore files that should not be in repository)
          .gitattributes                 (Git configuration file to configure repository, such as end-of-line handling.)
          mkdocs-project                 (If project is only documentation and MkDocs is used to create static website.)
          doc-dev-mkdocs-project         (Use for developer documentation created with MkDocs.)
          doc-user-mkdocs-project        (Use for user documentation created with MkDocs.)
      tools/                             (Software installed in the development files.
        software1/                        This may be appropriate if the software is not available on the operating system,
        software2/                        or a local install is needed to isolate from the operating system.)
         
```

The above file structure is illustrated with [specific examples for different languages](dev-env-by-lang/overview/).
An example for an Open Water Foundation Java REST web service application using Tomcat server and Eclipse IDE is as follows:

```text
$HOME/                                   (Developer's home folder /home/user on Linux/Cygwin, and C:/Users/user on Windows.)
  owf-dev                                (Top-level folder indicating where development projects will live)
    SomeDatabaseREST/                    (Folder containing project development files.)
      bin/                               (Folder containing scripts such as start-up script for IDE,
        scripts, etc.
                                          to ensure that proper development software versions are used.)
      eclipse-workspace/                 (Folder used by IDE workspace, when not appropriate for in Git repository.
                                          For example, the Eclipse IDE creates a .metadata folder under the workspace folder that
                                          is not generally suitable for storage in the repository because dynamic
                                          files will vary by developer.)
      git-repos/                         (Git repositories that contain files used in the software project.  Run the following here:
        repo-1-name/                      git clone https://pathToRepo.git
        repo-2-name/                      where the path to the repository is provided by GitHub, Bitbucket, etc.)
          README.md                      (Standard repository readme Markdown file explaining content and setup.)
          .gitignore                     (Git configuration file to ignore files that should not be in repository)
          .gitattributes                 (Git configuration file to configure repository, such as end-of-line handling.)
          mkdocs-project                 (If project is only documentation and MkDocs is used to create static website.)
          doc-dev-mkdocs-project         (Use for developer documentation created with MkDocs.)
          doc-user-mkdocs-project        (Use for user documentation created with MkDocs.)
      tools/                             (Software installed in the development files.
        tomcat8/
         
```

If everyone on the developer team uses a file structure as documented for the software project,
then relevant documentation can be created and used as a reference.
It may be necessary to split a project's development files into multiple projects,
for example in cases where multiple languages and tools are used.
The above example does not explore complex projects but assumes that a single primary software language is used.
The best way to understand project file structure is to examine good working projects.

## Next Steps ##

The next sections of this documentation describe how to install software development tools,
and how to use a file structure such as above to create a development environment for a software project.
