# Preface

    The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
    "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this
    document are to be interpreted as described in RFC 2119.

<https://tools.ietf.org/html/rfc2119>

# Abstract

This document is intended to serve as a quick reference to verify that your
project is ready to be shared with the rest of the world.

Brief overview:

- Code SHOULD have a test suite.
- Subversion repositories MUST have a sane directory layout.
- Release notes MUST be kept in subversion.
- Eclipse projects MUST be configured in such a way that projects may be opened from any workspace.
- `trunk` MUST have code review.
- Code MUST be documented with Doxygen, and there MUST be a relevant `Doxyfile`.
- Each project MUST have a "read me" file.

The sections that follow go into detail about the above guidelines.

# Test Suites

C code SHOULD have a related test suite.

There are a number of "xUnit" style testing frameworks. Pick one:

- [Check](https://libcheck.github.io/check/)
- [cmocka](https://cmocka.org/)
- [CuTest](http://cutest.sourceforge.net/)
- [Google Test](https://github.com/google/googletest)
- [greatest](https://github.com/silentbicycle/greatest)
- [libtap](https://github.com/zorgnax/libtap)
- [MinUnit](http://www.jera.com/techinfo/jtns/jtn002.html)
- [Wikipedia: List of unit testing frameworks](https://en.wikipedia.org/wiki/List_of_unit_testing_frameworks)

It does not matter which. Developers SHOULD aim for 100% code coverage.

# Subversion Best Practices

## Introduction To Subversion

Developers are encouraged to read read "Version Control with Subversion":

<http://svnbook.red-bean.com/>

## Repository Layout

Subversion repositories MUST have the following top level directory structure:

    .
    |-- branches
    |-- tags
    \-- trunk

Branches are where developers will develop their software solutions.

Tags MUST created *only* from a frozen `trunk`. This reduces the need to
do multiple code review sessions.

Subversion maintains author and creation date history. It is not necessary to
mention anywhere in source code when a feature was added, when a file was
created, who authored a file, or any such information.

# Release Notes

From "Version Control with Subversion":

    Your Subversion repository is like a time machine. It keeps a record of every
    change ever committed and allows you to explore this history by examining
    previous versions of files and directories as well as the metadata that
    accompanies them.

Subversion is the tool that SHOULD be used to review project history. Release
notes MUST be made against tagged releases, and commit messages MUST be
meaningful and descriptive of their changes.

# Eclipse Project Configuration

Eclipse projects MUST use variables of the form:

    ${workspace_loc:/${ProjName}/path/to/program.exe}

This is the portable way to configure an Eclipse project. The consequence
of configuring a project in this way is that the project may be imported
into any workspace.

# Code Review

All code merged into `trunk` MUST have a review session.

Branches and tags do not require review: Branches do not require review
because they are the primary way a developer will work on their code,
and any changes to code in a branch will be merged into `trunk` in order
to be distributed to other developers. As previously stated, Code MUST be
reviewed in order to be merged into `trunk`.  Tags do not require review
because `trunk` receives review, and tags MUST only be created from `trunk`.

# Code Documentation

Developers SHOULD use [Doxygen](http://www.stack.nl/~dimitri/doxygen/index.html)
to document their code.

All public header files MUST have complete Doxygen comments, describing
things that developers feel necessary. This list SHOULD include:

- Brief summary
- Detailed summary
- Code samples and usage examples

Developers who use Doxygen SHOULD provide a `Doxyfile` with their project.

Doxygen comes with a wizard application that
can be used to configure the `Doxyfile`:

<http://www.stack.nl/~dimitri/doxygen/manual/doxywizard_usage.html>.

Other forms of documentation are acceptable, but Doxygen is preferred.

# Project Summary

Each project MUST a "read me" file that may be titled "readme.txt" or
similar. This file SHOULD contain:

- Information about the project
- Steps to compile the project
- Steps to run the project
- Project dependencies

## Contributing

Other projects have a guide on "how to contribute to the project," in the form
of a file named "CONTRIBUTING.md." Here are some samples:

- <https://gist.github.com/PurpleBooth/b24679402957c63ec426>
- <https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md>
- <https://github.com/atom/atom/blob/master/CONTRIBUTING.md>

This file is intended to serve as an introduction for newcomers to the project.

## Hacking

Other projects have a guide on "how to hack on the code base," in the form of a
file named "HACKING.md." Here are some samples:

- <https://github.com/colah/ImplicitCAD/blob/master/hacking.md>
- <https://github.com/openshift/origin/blob/master/HACKING.md>

Your project may have a separate "read me" and "how to contribute" guides.

## Maintainers

Other projects have a guide on "who is maintaining what part of the code base,"
in the form of a file named "MAINTAINERS." Here are some samples:

- <http://git.qemu-project.org/?p=qemu.git;a=blob_plain;f=MAINTAINERS;hb=HEAD>

This file should list points of contact for personnel in charge of project
resources.
