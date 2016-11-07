# Software Development Tools / Text Editor

A text editor is a software program that allows text files to be edited.
Text files include software code, configuration files, and data files.
Software developers will rely heavily on text editors as they write code, create tests, and configure software.

Text editors have the following basic designs:

1. Keyboard-based editing in command shell window, such as `vim` and `emacs`, rely on keyboard characters for changing modes, and navigation.
These editors can be very efficient to use but require a time investment to learn.
2. Graphical user interfaces for editing, such as `Notepad`, `Notepad++`, `gvim`, `sublime`, `atom`,
provide navigation using arrow keys, scrollbar, and mouse.
These editors are typically easy to use but can offer many features that are seldom used.
3. Integrated Development Environment (IDE) include features of the previous case inside an integrated development environment.
Most serious developers will use an IDE because of code-completion, debugging, links to API documentation, and other features.
IDEs require time to learn, although a minimal level of proficiency can be enough for many software development projects.

Text editors may introduce side-effects that software developers need to be aware of:

* Different operating systems using different [end of line (newline)](https://en.wikipedia.org/wiki/Newline) characters.
Most text editors transparently handle.  However, primitive editors like Windows Notepad, may not properly show end of line characters
for files created on Linux-like systems, resulting in display of files as one line concatenated line.
In this case, use a more full-featured editor.
* Editors may create backup files to allow recovery from undesired editing sessions.
These files need to be ignored for [revision control](../dev-env-tools/revision-control/) so that they do not clutter the repository.
For example, use a `.gitignore` file to indicate filename extensions used for temporary files.

## Keyboard-based Editors

Need to describe in more detail, here, provide links.

## Graphical User Interface Editors

Need to describe in more detail, here, provide links.

## Integrated Development Environments

IDEs are discussed in a [separate section](../dev-env-tools/ide/).
