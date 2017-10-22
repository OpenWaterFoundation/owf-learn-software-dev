# Development Environment Tools / Documentation #

Software documentation tools for developers include:

* tools to convert code comments to API documentation
* tools to create formatted developer and user documentation

## API Documentation ##

Application programmer interface (API) documentation, which describes how to use code modules, can be created by:

1. embedding properly formatted comments in code
2. using software to process comments into API documentation

The format of comments to some degree depends on the programming language, although there are some tools that can handle generalized comments.
Specific tools are discussed in the documentation sections for each language, but several examples are:

* Java - [Javadoc](https://en.wikipedia.org/wiki/Javadoc)
* Python - [docstrings](https://en.wikipedia.org/wiki/Docstring) and [Sphinx](https://en.wikipedia.org/wiki/Sphinx_(documentation_generator))
* Multiple languages - [Doxygen](https://en.wikipedia.org/wiki/Doxygen)

Software developers should document their code and use these tools to generate API documentation, for use by their own team and other developers.

## Developer and User Documentation ##

Developer and user documentation, similar to this documentation, typically involve creating content of varying levels of detail to explain
how to develop, and use software, respectively.

The [Sphinx](https://en.wikipedia.org/wiki/Sphinx_(documentation_generator)) software can be used to generate navigable websites,
using reStructuredText (RST) files into HTML static websites.

The [MkDocs](http://www.mkdocs.org) software processes [Markdown](https://en.wikipedia.org/wiki/Markdown) files into HTML static websites, such as this documentation.

The source files for the HTML static websites can be maintained in a version control system, and the processed output can be placed on the web for use by developers.
