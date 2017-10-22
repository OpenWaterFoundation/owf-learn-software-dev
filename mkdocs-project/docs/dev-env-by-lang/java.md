# Development Environment by Language / Java #

A Java development environment will typically use an IDE such as Eclipse or NetBeans,
each of which impose certain conventions on the development environment.
The following focuses on an Eclipse development environment.

## Development Tools

A Java development environment will typically require that the following development tools are installed:

* Git - version control command line tools, in addition to those built into Eclipse
* Python/MkDocs - for developer documentation
* Java compiler - typically Java 8 and possibly Java 7
* Eclipse IDE - typically Mars are newer, and EE version if doing web development
* Tomcat - if doing web development, typically version 8

## Development File Structure

The following development file structure is an adaptation of the [general development file structure](../overview/#software-project-file-organization),
with the following main adaptations:

* `eclipse-workspace` is used for the Eclipse workspace folder, under which is typical `.metadata` folder with Eclipse workspace files
* the repository files adhere to Java organization.  If Maven is used for dependency management, then the file structure will adhere to
the Maven archtype and general Maven conventions
(see [Introduction to the Standard Directory Layout](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html)).
Each repository corresponds to an Eclipse project (each of which includes `.project` and `.settings` folders)
* Developer documentation uses Mkdocs and folder `doc-dev-mkdocs-project`
* User documentation uses Mkdocs and folder `doc-user-mkdocs-project`
* Not sure if any additional local tool installation is needed, although some may be added as this documentation is updated


```
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
      eclipse-workspace/                 (Folder used by IDE workspace, when not appropriate for in Git repository.
        .metadata/                        For example, the Eclipse IDE creates a .metadata folder under the workspace folder that
          .plugins/                       is not generally suitable for storage in the repository because dynamic
                                          files will vary by developer.)
      git-repos/                         (Git repositories that contain files used in the software project.  Run the following here:
        repo-1-name/                      git clone https://pathToRepo.git
        repo-2-name/                      where the path to the repository is provided by GitHub, Bitbucket, etc.)
          README.md                      (Standard repository readme Markdown file explaining content and setup.)
          .gitignore                     (Git configuration file to ignore files that should not be in repository)
          .gitattributes                 (Git configuration file to configure repository, such as end-of-line handling.)
          doc-dev-mkdocs-project         (Use for developer documentation created with MkDocs.)
          doc-user-mkdocs-project        (Use for user documentation created with MkDocs.)
      tools/                             (Software installed in the development files.
        software1/                        This may be appropriate if the software is not available on the operating system,
        software2/                        or a local install is needed to isolate from the operating system.)

```
