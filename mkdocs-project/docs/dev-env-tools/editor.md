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

See the [list of text editors](https://en.wikipedia.org/wiki/List_of_text_editors).

Text editors may introduce side-effects that software developers need to be aware of:

* Different operating systems using different [end of line (newline)](https://en.wikipedia.org/wiki/Newline) characters.
Most text editors transparently handle.  However, primitive editors like Windows Notepad, may not properly show end of line characters
for files created on Linux-like systems, resulting in display of files as one line concatenated line.
In this case, use a more full-featured editor.
* Editors may create backup files to allow recovery from undesired editing sessions.
These files need to be ignored for [version control](../dev-env-tools/version-control/) so that they do not clutter the repository.
For example, use a `.gitignore` file to indicate filename extensions used for temporary files.

Text editors may be integrated with other tools:

* Environment variables may be used by the operating system to automatically select a text editor program.
See the following for [Linux `EDITOR` environment variable discussion](http://unix.stackexchange.com/questions/4859/visual-vs-editor-whats-the-difference).
On Windows the editor may be set by associating an editor program with a file extension.
* Revision control software may have a configuration variable to specify the editor to use for editing, beyond the operating system default.
For example, for Git, the editor used to edit commit messages, etc. is set using `git config --global core.editor editorProgram`.

## Terminal Editors

Terminal editors use a normal terminal/console window, such as a Linux terminal window or Windows command shell window to edit a file.
Keyboard keys are used to navigate the file and perform editing actions.
These editors often have a long history since they were developed when graphical user interfaces were not available.
The advantage of such editors are:

* once the keystrokes are memorized, editing can be very fast
* because the interface does not rely on a graphical environment,
the editors may be the best option when accessing remote systems in a terminal window
* because the editors have been around a long time, they are often supported on may operating systems, devices,
and older computers
* many terminal editors also have a graphical version, allowing keystrokes for rapid navigation and editing
with the benefits of graphical user interface formatting

Disadvantages are:

* it is necessary to memorize editor keystrokes to be efficient and some people may not want to invest the time in learning
* the terminal window interface may not mark up files with colors, fonts, etc. the way that graphical editors do
(although many terminal editors do now provide automatic formatting based on file extension or other auto-detect features)

The following sections discuss useful terminal editors.

### vi or vim

The `vi` editor is a popular editor originally developed on Linux.  The newer [`vim` (Vi IMproved) editor](https://en.wikipedia.org/wiki/Vim_(text_editor)) is a newer version that
has a command-line (terminal) version and graphical version.
The `vim` editor is available for most operating systems through typical package install approaches (such as `apt-get` on Linux or Cygwin packages) or stand-alone installers.

See the following resources to learn `vim` although there are many available online:

* [Vim official website](http://www.vim.org/)
* [A Great Vim Cheat Sheet](http://vimsheet.com/)

A `.vimrc` file can be created in the user's home folder to control common behavior of the editor.
These settings can also be set when editing a file by using a colon (`:`) before the setting shown below,
but will revert to defaults when the editor is closed.
This is useful to understand the setting before including in the startup file.
Useful settings that can be entered into the startup file are as follows:

Setting example | Description
--------------- | --------------
`colorscheme schemename` | Specify the color scheme name for `syntax` setting formatting.
`syntax on`      | Turn colored syntax formatting on.
`set ic` | Ignore case when searching.
`set spell` | Enable spell-checker and highlight misspelled words.

`vim` editor features may be offered in other editors and IDEs, to facilitate software developers that prefer to use `vim` key combinations.

### emacs Editor

[Emacs](https://en.wikipedia.org/wiki/Emacs) is another popular editor.
In contrast to the `vim` editor, `emacs` uses more Ctrl-, Alt- keyboard combinations.

### Nano Editor

See: [Nano](https://en.wikipedia.org/wiki/GNU_nano).

## Graphical User Interface Editors

Graphical user interface editors provide editing in an interactive window that responds to mouse events, scrolling, etc.
These editors provide *what you see is what you get* (WYSIWYG) editing.
Navigation and editing commands typically have short-cuts through keyboard combinations.
For example, Ctrl-C may be used for copy, Ctrl-v for insert, Ctrl-s for save.
However, this is difficult to fully standardize across tools.
There is a trend that editors are enhanced over time and some become similar to full IDEs.
Software developers can evaluate whether to use such editors rather than an IDE such as Eclipse but need to understand
the implications on configuring a software project's file structure and impacts on other developers.

Some useful graphical editors are:

* [Notepad++](https://en.wikipedia.org/wiki/Notepad%2B%2B), available on Windows
* [Sublime Text](https://en.wikipedia.org/wiki/Sublime_Text)


## Integrated Development Environments

IDEs are discussed in a [separate section](../dev-env-tools/ide/).

IDEs typically provide graphical user interface editors.
Plugins may be available to emulate the behavior of specific editors,
for example the [Vrapper plugin for Eclipse](http://vrapper.sourceforge.net/home/).

Selecting an IDE is usually a more serious choice than selecting an editor and the software developer may
just need to learn to use the IDE editor rather than trying to customize or use their favorite text editor.
Most IDEs provide good editors.
The more customization of a development environment or editor that creeps in (such as requiring plugin installation),
the more difficult it is to help other software developers use the same environment.
