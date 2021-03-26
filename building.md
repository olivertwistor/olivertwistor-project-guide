# Building

## Build project
Depending on the programming language and environment used, the build process might vary. You may be using Ant, Gradle, Maven or something else. The end result may be a JAR file, and EXE file, a WAR file or something else. Regardless, there are build versions that every release must have.

All build scripts shall be checked into GitHub. For more details on how to make these builds, please refer to the manual of respective build tool.

### Runnable executable or library with compiled code
This is the most important build. It should contain the following items:

* If executable:
    * the executable file(s) needed to run the application
    * any external configuration files, databases or non-compiled assets needed to run the application (if applicable)
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
This build is the most complete of these four listed. It should contain the following items:

* all source code files (including test source code)
* configuration files and assets/resources
* readme file(s)
* license file(s)
* contributing guidelines
* changelog
* build files for all build versions

### Generated documentation files
This build is a little special, because it should only contain generated documentation, such as Javadoc.

1. Generate the documentation with an appropriate tool, for example doxygen or Javadoc.
1. If the generation tool doesn't pack the files into for example a JAR file, pack them yourself in a JAR file, a ZIP file or any other appropriate container. The end result should be one single file containing all documentation.


[1]: https://semver.org/
