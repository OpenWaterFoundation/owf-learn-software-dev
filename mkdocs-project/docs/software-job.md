# What Job will the Software Do?

Software programs perform a task, quite often one that a human could do themselves (like math, or drawing a picture),
but the software can do the job faster, in a repeatable way, and work input and output can be saved in electronic form so that it can be shared and modified later.

The first question to ask might be "What Job will the Software Do?".
There are many answers, and the more specific the job is, the more specific the answer will be.
For example, consider the following answers to the above question (in this case related to a job related to water):

* I need a program that will displays maps.
* I need a program that will displays maps in my web browser on my computer.
* I need a program that will displays maps in my web browser on my computer and phone.
* I need a program that will displays maps in my web browser on my computer and phone that lets me add river photographs and other data at a point.
* I need a program that will displays maps in my web browser on my computer and phone that lets me add river photographs and other data at a point and share with others.
* I need a program that will displays maps in my web browser on my computer and phone that lets me add river photographs and other data at a point and share with others,
some of whom are color-blind.

The above answers illustrate that it can be complicated to describe the full purpose of a software program.
And, before trying to develop a new program, most people will try to find an existing program that will do the job that they need.
Perhaps more than one software program will be needed to do a job (such as creating a spreadsheet to analyze data,
and then pasting the spreadsheet table into a document).

## Use Cases and Requirements

Describing a job that software will do is often called a *use case*, *user story*, or simply *story*.
In the past it was common that software requirements would be defined in a very detailed way ("the software shall do X"),
and such requirements would in their entirety define the software development team's scope of work.
The software would not be accepted until all the requirements were met.
Today an agile methodology is often used, where the user-facing aspect of a software project is stated more generally as a story,
and software teams are responsible for translating the story into design and developing the software (see section below).

Other aspects of defining the software may include:

* What operating system (types of computer devices) will the software need to run on?
* Does the software need a graphical user interface or command line interface?
* Is a web application needed (something that runs in a web browser)?
* What user authentication and security features are needed?
* How fast does the software need to run?
* What are the software inputs and outputs?
* Who will own the software and is it open source or proprietary?
* Who will maintain the software?

Clearly, all of these questions go beyond "What job will the software do?" and it should be clear that things can get complicated,
which is why there is a need for software development knowledge and skills.
It is likely that a few key requirement constraints are already defined at the start, such as:

* The people or organization(s) that are interested in running the software (because they have a job to do)
* The device(s) the software needs to run on (because the organization(s) have invested in certain devices)
* The operating systems that the software needs to run on (because the device(s) use certain operating systems)
* Related software or technologies (because often systems of multiple programs are needed to do a jobs)

There is no single software program that does every job in the world and therefore it is necessary to constrain each
software program's functionality, and integrate multiple software programs to do more complex jobs.
The above constraints will provide general background for the software before digging into internals such as the programming language.

## Buy or Build?

Before developing new software, it is often useful to understand whether an existing software tool can do the job.
Why spend time developing new software and deal with future maintenance costs of such software when existing software can do the job?
If existing software can be found, great, but the following illustrates cases when creating (building) new software may be appropriate:

* software is being developed as a learning exercise, such as by students or someone learning a technology at work
* there is a software product available, but the cost and/or proprietary nature of the software limits its adaption and applicability for the job
* there is clearly not a viable software product available to do the job
* a software product is available as a platform (see next section), but an additional increment of software needs to be developed 

Be aware that developing software can be expensive, especially if it is complex and has rigorous quality requirements.
However, due to the pervasiveness of computers and other technologies, there is a fundamental need to be able to create software to do jobs.
The goal is to develop software as effectively and as efficiently as possible.

The more complex or specialized a job is, the greater the likelihood that software may need to be developed or enhanced.
Think of it this way...the fewer opportunities there are to "sell" an out-of-the-box software program,
the more specialized the software is and the higher the incremental cost of that software will be
(where cost will be higher if the complexity of the software is higher).

Assuming that the approach is to build new software (or add on to existing software), the following sections provide additional background.

## The Concept of Platforms, Frameworks, and Open Specifications

New software can be developed totally from scratch but seldom is.
A software developer typically finds existing building blocks to use so that they don't have to create everything.
A platform is the underlying hardware and software on which a solution is created, such as the operating system, database, etc.
Furthermore, a framework is a set of software libraries and standards that defines the solution - a framework provides structure
such as an application programming interface ([API](https://en.wikipedia.org/wiki/Application_programming_interface)).
A framework may offer more flexibility because it conceptualizes a solution across platforms.
Having said this, it is not critical to get caught up in semantics at this stage.
What is important is to recognize that there are different foundational technology concerns that should be considered and leveraged when developing software, such as:

* the programming language (whether a primary programming language or a domain-specific language) that is used for the software will provide many core features
* add-on libraries and plug-ins will extend the core language to provide additional features
* a software solution may involve several layers of platforms/frameworks, for example a [spatial database](https://en.wikipedia.org/wiki/Spatial_database)
built on structured query language ([SQL](https://en.wikipedia.org/wiki/SQL)) for queries,
working with a database product, running on a certain operating system

It can be temping to use all of the custom features of a platform, framework, or technology.
However, doing so can lock in a solution to a product and limit future options.
One way to avoid lock-in is to choose open platforms and frameworks that focus on higher-level concepts (such as time series and map layers for data),
and furthermore to use open specifications, such as for data exchange.

A fundamental choice of a platform is the language that is being used.
Luckily, most programming languages today are already open specifications and most have a variety of free and not-free development tools
that provide flexibility in making decisions and changing approach in the future.
An additional level of open specifications is data formats for exchange between programs and persistence.
For example, the [JavaScript Object Notation (JSON)](http://www.json.org) format has become quite popular because of its open nature.
A solution that uses JSON will be more easily integrated with other software than a solution that uses proprietary data formats (assuming that JSON can do the job).

The benefit of selecting a platform/framework for a solution is that it typically provides substantial functionality and in many cases
has predefined guidelines for approach so that the software developer does not need to reinvent fundamental functionality and can follow a standard approach.
The following illustrate different considerations when choosing a platform/framework:

* programming language and available libraries/plugins may provide significant features
* platform/framework may provide built-in graphical user interface, one of the more difficult components to develop
* platform/framework may provide operating system portability (or not)
* platform/framework may have associated developer tools such as integrated development environment (IDE) 

The main point is that rather than developing a software program from scratch using only the basic programming language,
it may be appropriate to select a platform/framework that has already provided much of the solution.
In this case, the platform/framework may provide software patterns, domain-specific-language (macro language),
or other features to make development easier.

## Open Source Software

The Open Water Foundation is a proponent of open source software, but we also understand the reasons why proprietary software may have benefits.
Ultimately, organizations must make money to pay for the products and services solutions they provide.
Revisiting the question "What job will the software do?" will identify one or more open source and proprietary software programs.
The benefit of open source software and open standards is transparency to understand the context of the solution,
being able to troubleshoot bugs, and, if the software is free, an ability to try a solution before investing a lot of resources.
However, open source software may suffer from lack of resources if not sufficiently funded,
 and consequently the pace of development and support may be slow,
depending on the size of the developer community and leadership for the open source project.
It is also reasonable to expect that regardless of the cost and openness of the software,
businesses may charge for support, training, and other professional services.

This and other documentation created by OWF will refer to open source and proprietary software as appropriate,
with a preference for open source software when such software can do the job.

## Agile Methodology

An agile methodology recognizes that spending a lot of time writing detailed requirements documents is problematic because it takes a lot of time,
the requirements will never be complete, and they will change.  Instead, an agile approach defines high-level requirements based on user needs (user stories) and
allows developers to work on the details of implementation.  Quite often, the requirements will change as the solution converges.
An agile approach, when used by a software development team, can achieve rapid results.
However, an agile approach still requires a proper roadmap, guided by those with subject matter expertise,
to ensure that the development will hit the target.
It is important that software developers and domain experts work together.
The following are resources that illustrate an agile methodology:

* [Scrum on Wikipedia](https://en.wikipedia.org/wiki/Scrum_(software_development))
