# Software Development Tools / Compiler

Software generally falls into two categories:

1. Software code that must be compiled into an executable program that the computer understands, using a [compiler](https://en.wikipedia.org/wiki/Compiler) for the programming language.
2. Software code that is NOT compiled but requires an [interpreter](https://en.wikipedia.org/wiki/Compiler) to run.

The choice of whether to use a compiler or interpreter will generally depend on the programming language that is chosen for the software being developed.

## Compiled Software

A software compiler translates the software code, written using the syntax of a specific programming language,
into executable programs that the computer can natively understand and run.
In other words, the operating system knows how to load the executable program into memory and execute its instructions.
For performance reasons, executable programs are typically binary files, meaning that they cannot be easily understood when viewed in a text editor.

Examples of compiled languages include C, C#, Fortran, and Java.

Language compilers also check code for syntax errors and handle references to software libraries, classes, modules, packages, etc.,
where the terminology that is used depends on the language.
Each software program contains its own code, and also typically utilizes other code that is available in operating system libraries,
[runtime libraries](../dev-env-tools/runtime/), or third-party libraries.

Many software compilers are now available free of charge, although some are commercial products.
The compiler that is chosen typically depends on the programming language.
See the documentation sections that focus on programming language for more information.

## Interpreted Software

Interpreted software uses a runtime interpreter to run the software.
Examples of interpreted languages include:

* "batch" files in Windows, run with `cmd.exe` program on Windows 7 and Windows 10
* "scripts" in Linux, run with shell program such as `bash`
* Python programs, run with Python interpreter
* JavaScript in web applications, run in web browsers

Advantages of interpreter programs are that the software logic can be directly viewed as text and can be edited in deployed software.
Disadvantages are that interpreted programs are usually slower because code syntax must be parsed and error-checked at run-time,
and there are trade-offs in robustness, security, etc.

In the end, a software developer needs to evaluate whether an interpreted language approach is appropriate.

## Software Systems

Many software systems use a combination of compiled and interpreted software.
Actually, an interpreter is a compiled program that knows how to interpret instructions.  Examples include:

* Database query software that provides an interactive shell, which calls underlying compiled query software.
* Command prompt for operating system, which calls compiled programs to do work.

Although it is possible to write more and more code that compiles into a huge program,
most software solutions involve using a number of compiled and interpreted software programs.
Integration can be improved by using open data specifications.
