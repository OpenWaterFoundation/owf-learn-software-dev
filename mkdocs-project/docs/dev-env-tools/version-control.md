# Software Development Tools / Version Control

Version control is very important in software development because it allows software developers to change code and
have confidence that they can back up to a previous version if necessary.
Changes are tracked and simplify troubleshooting by pointing out where changes were made that broke a software feature.

Version control can be used on any type of file, including code, other text files, documentation, tests, dependencies, etc.
In general, only original representations of content should be saved, not dynamic output.
For example, software code should be versioned, but compiled executables should not because they can be recreated from code.

This documentation is maintained in a [GitHub repository](https://github.com/OpenWaterFoundation/owf-learn-software-dev).

Unfortunately, it can be difficult to do version control right unless the software is used regularly.
One-person development teams can get away with basic version control,
but each developer on a multi-person team must must be proficient and follow the version control approach adopted by the team.

## Potential Issues

The following issues can arise when using version control systems:

* Code format issues.  Software code can typically be formatted different ways.  For example tabs or spaces can be used for indent.
How many spaces equal a tab?  Formatting should be defined for the software development team and be enforced by the
person(s) that commit changes to the repository.
* End of line issues.  Different operating systems use different end of line characters and many lines may be
indicated as having been changed, even though it was only line endings that changed.
These must be handled or else software developers working on different operating systems will use conflicting line endings.
* Merge conflicts.  Different developers might edit the same code and make conflicting changes.
A protocol must be put in place in the software development team to handle.
Version control software provides features to automatically merge edits and provide opportunities to deal with conflicts.
Merge conflicts can be alleviated by adopting a workflow for version control.
* Unwanted content can be saved in a repository.  Unwanted content, such as large binary files, passwords, temporary files, etc.
may accidentally be saved in a repository.  Version control systems have features to remove such files and
add configuration to ignore certain files (see Git `.gitignore` file).

## Simple File or Directory Copy

The simplest form of version control is to create copies of files or directories, for example using a date or timestamp in the file/folder name. 
This approach can be effective for simple software projects involving one software developer.
However, it does not scale well when there are many files and multiple software developers involved.

## Version Control Systems

Version control systems keep track of files in a *repository*, which is typically a custom database using a file hierarchy and compression to keep the repository size small.
The repository tracks revisions as an internal identifier (unique integer and/or hash string), and files in the repository are associated with a revision.
Different version control systems take different approaches.  For example, some store deltas (differences) between file revisions,
and others store the complete file each time there is a modification.
Most systems use compression to minimize file size.

## Distributed Version Control Systems

Distributed version control systems have become popular recently due to a number of factors including the need to support
distributed software development teams, the relatively low cost of disk storage, and the relatively high speed of the internet.
Distributed version control means that each developer has an entire copy of the repository on their local computer.
This ensures that they have full access to all saved revisions (in case they need to do a comparison or revert to an earlier version),
performance is fast because files are local, and it provides redundancy in case the server is unavailable.

Distributed version control systems typically rely on a master copy of the repository.
Content is maintained in one or more branches, where a *master branch* typically contains official versions that should always compile.

One or more developers with commit privileges do final integration of other developers' edits into the master branch.

The Git version control system is widely-used.  See [Open Water Foundation / Learn Git](http://learn.openwaterfoundation.org/owf-learn-git).
