# Software Development Environment Tools / Runtime Environment

Some programming languages rely on a runtime environment to run the software
rather than using compiled executable programs that are run directly by the operating system.
Runtime environment types include:

* interpreter
* virtual machine for compiled software

The following sections describe each.

## Interpreter

Interpreters are used to run software code that is written in text form and not compiled,
sometimes referred to as scripts.
The interpreter must parse the code, interpret the syntax, check for errors, and then run the script logic.
Examples of interpreted languages include:

* JavaScript, run in a web browser or Node.js interpreter
* Perl, run in Perl interpreter
* Python, run in the Python interpreter

## Virtual Machine for Compiled software

The term "virtual machine" is often used for operating systems, such as using VirtualBox to run Linux on a Windows computer.
The term is also used for some compiled programs that run within a specific virtual machine.  Examples are:

* [Java Virtual Machine (JVM)](https://en.wikipedia.org/wiki/Java_virtual_machine), provided by the Java Runtime Environment (JRE), used to run compiled java programs
* [Microsoft .NET framework](https://en.wikipedia.org/wiki/.NET_Framework)

The virtual machine provides a standardized environment that sits on top of the operating system but otherwise provides a complete environment
for running software.
This is particularly effective when the virtual machine can run on different platforms.
The software that is being run is compiled ahead of time into binary form.  For Java, source files are compiled into "bytecode" distributed
as individual class files or multiple class files in a Java archive (jar) file.

The Java virtual machine is used by other languages that are compiled to the same binary form.  See [List of JVM languages](https://en.wikipedia.org/wiki/List_of_JVM_languages).
Similarly, the .NET framework is the common runtime environment for several Microsoft languages (C#, Visual Basic, etc.), that compile to .NET assembly files.
