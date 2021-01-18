# Building

## Release schedule
I find it difficult to know when it's time to release a new version of the 
project I'm working on. Therefore, I think it's more convenient to decide in 
advance on intervals in time for releases, and depending on how much work has 
been done, set the new version number [accordingly][1]. 

A note on version numbers: release your 1.0.0 version as soon as possible 
(even if your project is not "finished" or "stable", whatever that means in 
today's world of software), especially if that project is a library. That way, 
it will be easier for other people who use your project to be confident of 
which new releases break their own code or workflow and which releases that 
can be downloaded without problems. The reason to move away from 0.x releases 
as quickly as possible is that *[Semantic Versioning][1]* allows 0.x releases 
to break or not for any version.

The optimal interval between releases will change between projects and how much 
work you're going to do in that time period. You neither want to have too small 
releases nor too big. My suggestion would be to delay setting a release 
schedule until a bit later in the project, when you have had time to get a feel 
of how long it takes you to be finished with an appropriate amount of work.

Larger bug fixes and security patches should always be released as soon as 
possible, though.

## Build project
Depending on the programming language and environment used, the build process 
might vary. You may be using Ant, Gradle, Maven or something else. The end result may 
be a JAR file, and EXE file, a WAR file or something else. Regardless, there 
are build versions that every release must have.

All build scripts shall be checked into GitHub. For more details on how to make 
these builds, please refer to the manual of respective build tool.

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

1. Generate the documentation with an appropriate tool, for example doxygen or 
Javadoc.
1. If the generation tool doesn't pack the files into for example a JAR file, 
pack them yourself in a JAR file, a ZIP file or any other appropriate 
container. The end result should be one single file containing all 
documentation.

## Create GitHub release
Releases on GitHub provide a way to store binaries, documentation and source. 
Each milestone should have its own release. Here's how you create one:

1. On the GitHub repository front page, press the *Code* tab. It may be 
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


[1]: https://semver.org/
