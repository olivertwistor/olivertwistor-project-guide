# Milestone release

## Release branch naming
Release branches should be named the same as their corresponding milestone. For 
example, if the milestone is named `1.7.4`, the release branch should be named 
`release/1.7.4`.

## Build project
Depending on the programming language and environment used, the build process 
might vary. You may be using Ant, Gradle or something else. The end result may 
be a JAR file, and EXE file, a WAR file or something else. Regardless, there 
are build versions that every release must have.

All build scripts shall be checked into Github. For more details on how to make 
these builds, please refer to the manual of respective build tool, such as Ant 
or Gradle.

### Runnable executable or library with compiled code
This is the most important build. It should contain the following items:

* If executable:
    * the executable file(s) needed to run the application
    * any external configuration files, databases or non-compiled assets needed 
    to run the application (if applicable)
    * readme file(s)
    * license file(s)
    * changelog
    * user manual (if applicable)
* If library:
    * compiled code packaged in a DLL, JAR or the like
    * any external configuration files (if applicable)
    * readme file(s)
    * license file(s)
    * changelog
    * user manual (if applicable)

### Source code without tests
This is also an important build. It should contain the following items:

* all source code files (excluding test source code)
* configuration files and assets/resources
* readme file(s)
* license file(s)
* contributing guidelines
* changelog
* build files for all build versions

### Source code including tests
This build is the most complete of these four listed. It should contain the 
following items:

* all source code files (including test source code)
* configuration files and assets/resources
* readme file(s)
* license file(s)
* contributing guidelines
* changelog
* build files for all build versions

### Generated documentation files
This build is a little special, because it should only contain generated 
documentation, such as Javadoc.

1. Generate the documentation with an appropriate tool, for example Doxygen or 
javadoc.
1. If the generation tool doesn't pack the files into for example a JAR file, 
pack them yourself in a JAR file, a ZIP file or any other appropriate 
container. The end result should be one single file containing all 
documentation.

## Create Github release
Releases on Github provide a way to store binaries, documentation and source. 
Each milestone should have its own release. Here's how you create one:

1. On the Github repository front page, press the *Code* tab. It may be 
selected by default.
1. Press the button *x releases* (where x is the number of releases the 
repository has so far).
1. Press either the button *Create a new release* (if there are no previous 
releases) or *Draft a new release* (if there is at least one previous release).
1. For the *Tag version*, write the same name as the tag you created, for 
example `v1.7.4`.
1. In the dropdown list *Target*, choose the `master` branch.
1. Write the same in *Release title* as in *Tag version*.
1. Write release notes in the text box *Describe this release*. This should be 
the most recent update to the `RELEASE.md` file, or at least a condensed 
version of that.
1. *Attach* four files:
    * runnable executable or library with compiled code
    * source code without tests
    * source code including tests
    * generated documentation files
1. Leave the checkbox regarding pre-release empty. I don't use pre-releases, 
but if this release really is one, go for it and check the box.
1. Press the *Publish release* button. You can also save a draft by pressing 
the *Save draft* button.

## Installation instructions
In this section of the readme file, you will write step-by-step instructions on 
how to install and configure the application, library or whatever your project 
is. All the necessary prerequisites should also be listed, including on how to 
download and install those (or preferrably links to their own instructions, as 
they are more likely to be more accurate and updated).

Be as specific as possible when listing prerequisites and their version 
numbers. By using build tools such as [Ant][1] or [Gradle][2], this step may be 
easier for the user because you as the developer is in more control over 
dependencies and prerequisites.

## Usage instructions
In this section of the readme file, you will write how to use the application, 
library or whatever your project is.

[1]: https://ant.apache.org/
[2]: https://gradle.org/
