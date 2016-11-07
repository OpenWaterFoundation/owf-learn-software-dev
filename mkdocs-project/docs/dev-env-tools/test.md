# Software development Environment Tools / Testing Framework

Automated testing is very important to ensure software functionality and quality.
The basic approach for software testing is to run tests and compare current output with expected results.

Each programming language and software development environment provides tools for testing.
Additional detail is provided in the language-specific sections of this documentation.

# Unit Testing

[Unit testing](https://en.wikipedia.org/wiki/Unit_testing) is typically implemented within the development environment and directly calls software routines.
For example, a function is called to generate output, which is compared to the expected output.
Unit tests typically use a testing library with basic building blocks for testing.

Unit testing is typically performed by the software developer and in automated tests before shipping software.

# Functional Testing

[Functional testing](https://en.wikipedia.org/wiki/Functional_testing) involves running installed software to ensure that functionality is as expected.
An approach similar to unit testing can be taken.
However, the testing framework must allow execution of the software in installed form, without developer environment.

Functional testing frameworks may be language-agnostic but may instead focus on an operating system or platform.
For example, the [Avacodo testing framework](https://avocado-framework.github.io/) on testing Linux components.

Functional testing is typically performed by the software developer and in automated tests before shipping software.
It can also be performed by software users and support to confirm that software is working after installation.
