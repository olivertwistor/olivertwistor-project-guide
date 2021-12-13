# Olivertwistor Project Model
This is my project model that I'm using with all my programming projects. It includes both instructions and templates.

## Installation
You can either read all the documents in this repository [online on Github](https://github.com/olivertwistor/olivertwistor-project-model) or [download them for offline use](https://github.com/olivertwistor/olivertwistor-project-model/releases).

## Usage
Follow the section [Installation](#installation). If you're using this model as a template for your own projects, feel free to skip any steps that doesn't fit your particular project.

## Licenses
The files in this repository are licensed under a [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) license. For detailed license terms, please read [LICENSE](LICENSE).

## Project instructions
In this section, I will describe the steps I take when working with a project, from start to finish. Try to follow each step in the order they are written, but don't be afraid to go back to previous steps if you need to add or change something. After all, software development is an iterative and incremental process. 

If something does not suit your needs, feel free to change it. Remember that these are the steps *I* take; they may not necessarily be the steps *you* want to take.

**Important: The following steps assume you are the only developer. If multiple people are working with the same project, steps must be added to accomodate scheduling of resources and working on tasks.**

### Create a new repository
These instructions presume that you already have a Github account and are logged in.

1. Go to https://github.com/new
1. Choose a *Repository name*.
1. Write a short *Description* of what the project is about.
1. Choose between making the repository *Public* or *Private*. Public repositories are to be preferred since making it open source gives back to the community. For client work and similar things, choose *Private*.
1. Press the button *Create repository*.

### Add basic documentation
The repository should have the following repository documentation, placed in the root of the repository:

* `README.md` ([template](templates/template-readme.md "README.md template"))
* `LICENSE` ([template](templates/template-license.md "LICENSE template"))
* `CONTRIBUTING.md` ([template](templates/template-contributing.md "CONTRIBUTING.md template"))
* `CHANGELOG.md` ([template](templates/template-changelog.md "CHANGELOG.md template"))

In addition to a `CHANGELOG.md`, a `RELEASE.md` ([template](templates/template-release.md "RELEASE.md template")) may be useful if there are big differences between change notes that would benefit other developers and end-users.

### Create a work breakdown structure
In a work breakdown structure (WBS), the goal is to capture the totality of tasks needed for the project to be completed. This can be difficult to do, especially in software development where there are so many unknowns in the beginning. Don't worry if you won't capture all tasks in one go. Just try to capture as many tasks as possible; you can always return to this step later.

For now, the order of the tasks aren't important, we'll cover that in the next section when we'll make a network diagram. Just focus on capturing as many tasks as possible.

The WBS should go into a Markdown file in the `repo-docs/` folder. Name the file `wbs.md`. The following table shows an example of a (partial) WBS for a calculator app:

| Issue ID | Description
| :---: | :---
| 1 | Design the buttons
| 2 | Lay out all the UI components
| 3 | Write help text
| 4 | Make all strings translatable
| 5 | Make all numbers locale-aware
| 6 | Make the app fully keyboard accessible
| 7 | Define basic arithmetic
| 8 | Define statistical functions
| 9 | Enable exporting calculations to text file

Some of these tasks probably could be broken down further, depending on how granular you want your workflow to be. Don't be afraid to break up tasks or fuse them together after you've started working. It's often not until you're working you'll discover the right granularity. It also depends on the particular project.

However, please note that the completion of each task must leave the project in a stable and releasable state. [Each completed task is its own release.](#creating-a-release)

### Create a network diagram
With the work breakdown structure in place, it's now time to create a network diagram. In this step we'll define an order to all tasks, as well their dependency relationships. Some tasks may be quite independent and could be worked on whenever and in parallel with other tasks, but most tasks are either dependent on the completion of other tasks or have dependent tasks themselves.

A network diagram can either be created as a mind map or a table. I prefer to make a table, an example of which I'll show below. I'm using the same calculator app example as in the previous section. Note that this is the same table as in the WBS section, with dependencies added.

| Task ID | Description | Depends upon |
| :---: | :--- | :---: |
| 1 | Design the buttons
| 2 | Make the app fully keyboard accessible | 6
| 3 | Write help text
| 4 | Make all strings translatable | 3
| 5 | Make all numbers locale-aware | 1, 6
| 6 | Lay out all the UI components
| 7 | Define basic arithmetic
| 8 | Define statistical functions | 7
| 9 | Enable exporting calculation to text file | 7

As you can see, it's possible to have both one-to-many dependencies and many-to-one dependencies. For example, when you're finished with task #6, you may proceed with task #2, but not task #5 before you're also finished with task #1. Unfortunately, GitHub doesn't provide a way to express these kinds of relationships. Apart from managing a network diagram yourself, the only thing that GitHub can help with regarding this is milestones. We will however not use milestones in this model.

Now, we need to reorder the tasks in such a way that doesn't break any dependencies. I keep it simple and sort the tasks by ID, but you can sort them by estimated time cost or something else. You can see the results of that in the following table:

| Task ID | Description | Depends upon
| :---: | :--- | :---:
| 1 | Design the buttons
| 3 | Write help text
| 4 | Make all strings translatable | 3
| 6 | Lay out all the UI components
| 2 | Make the app fully keyboard accessible | 6
| 5 | Make all numbers locale-aware | 1, 6
| 7 | Define basic arithmetic
| 8 | Define statistical functions | 7
| 9 | Enable exporting calculation to text file | 7

Note that task #6 is moved up before both tasks #2 and #5. The reason why task #4 comes before task #2 is that I sort the tasks by ID.

Check in the network diagram file into version control under the folder `repo-docs/`. Name the file `network.md`.

### Work on tasks
Whenever you are ready to work on a task, take a look at the network diagram and pick the task at the top. Please take care to not choose a task which is dependent upon one or more other tasks.

#### Branching
Since I'm working alone, I don't have need for a complex branching model such as [Vincent Driessen's branching model](https://nvie.com/posts/a-successful-git-branching-model/). My branching model makes use of just two branches: `master` and `develop`. At the start of the project, create both branches so they contain the exact same content.

* The `master` branch holds stable and released code. Anyone should be able to check out any commit on this branch and be able to successfully build the project.
* The `develop` branch holds code under development. None of it should be considered stable or released. This branch is where the bulk of the commits are.

If you're going to do some experimental work with which you don't want to pollute the `develop` branch, you should create a separate branch with the prefix `feature/`. That way, you are free to remove the whole branch if the experiment failed, and no other code will be affected.

The `develop` branch should always be at the same level or ahead of `master`, since `develop` is the most recent non-stable snapshot of the project.

While working on a task, commit often so each commit won't have too many code changes. That way, it will be easy for you and others to see what's done, and if something went wrong, where it happened. Don't be afraid to push your changes to the remote repository on GitHub, either. That way, other contributors and even visitors to your project's GitHub page can see your progress.

#### Testing
Testing is a good thing, but can be difficult to get done. It should be done wherever and whenever feasible. I'm not very strict about it, though. Sergey Kolodiy have written an excellent [article about unit testing](https://www.toptal.com/qa/how-to-write-testable-code-and-why-it-matters), which I recommend reading.

Each project should detail the testing frameworks in use, in their respective `README.md` file. Test code should be committed to the Git repository so other contributors can benefit from it.

#### Documentation
Documentation is very important, both for your own sake and the consumers of your code. When working with others or when I'm reviewing other people's code, I often find myself having to closely study the code due to lack of documentation. Ideally, you should be able to get a grasp of what a class or interface, a method or function, or a chunk of code does by only looking at the documentation instead of having to delve into the code.

On top of documenting the code, there is need for documentation outside of the code as well. Please refer to the section [Add basic documentation](#add-basic-documentation) for templates for that.

#### Completing a task
When you are done working with a task, follow this checklist:

1. Make sure that every test passes, and that your code hasn't broken anything else in the code.
1. Under the heading *Unreleased*, update both `CHANGELOG.md` and `RELEASE.md` with the changes you've made to the project with this task. `CHANGELOG` is aimed towards other developers, while `RELEASE` is aimed towards end-users.
1. If applicable, update `README.md` with more information about installation and usage. Remember to update the license information as well, if you have made use of a new library for this task.
1. Commit and push the `develop` branch one final time (this assumes you have worked on the `develop` branch). 
1. Create a new branch from the `master` branch. Call it `staging`.
1. Try to merge `develop` with `staging`.
1. If there are no merge conflicts, proceed to the next step. Otherwise, read on:
    1. Resolve all merge conflicts.
    1. Make sure that every test passes, again, and that your merge hasn't broken anything else in the code.
    1. Commit and push the `staging` branch.
1. Merge the temporary branch with `master`. Resolve any conflicts by always choosing the changes from `staging` over `master`.
1. Remove the `staging` branch, both locally and remotely on GitHub.
1. Merge `master` with `develop`.

### Create a release
Since in my branching model the `master` branch holds stable and releasable code at all times, almost every commit to that branch can be interpreted as a release. Thus, every completed task is also its own release.

For each new release, follow these steps:

1. [Decide on a name for the release.](#naming-releases)
1. Move everything under *Unreleased* in `CHANGELOG.md` and `RELEASE.md` to a section with the new release name.
1. [Make builds of the project.](#build-the-project)
1. [Create a new GitHub release](https://docs.github.com/en/github/administering-a-repository/managing-releases-in-a-repository#creating-a-release) and attach all builds made in the previous step. The release should be created with a new tag with the chosen release name. As the description, paste the release notes from `RELEASE.md` for this release.
1. Merge the `master` branch with `develop`.

#### Naming releases
Releases can be found at the GitHub repo URL appended with `/releases`, for example [Olivertwistor Project Model's releases](https://github.com/olivertwistor/olivertwistor-project-model/releases). They should share names and follow [Semantic Versioning 2.0.0](https://semver.org/).

Semantic Versioning dictates that version numbers follow a specific pattern: `MAJOR.MINOR.FIX`. A *3.1.4* version number means that it's the third major release of this project, the second minor release within that major release (the first `MINOR` is always a zero), and the fifth fix within that minor release (the first `FIX` is always a zero). You may use the following list to determine whether a particular release constitutes a `MAJOR`, `MINOR` or `FIX` version.

* Applications
    * Major releases mean big changes or additions in functionality, resulting in brand new ways of using the application.
    * Minor releases mean smaller changes or additions in functionality, for example that the user can save a file in PDF format in addition to TXT, as was the case previously.
    * Fixes mean bug fixes or other very small things that don't involve a change in functionality. This can be things both visible and invisible to the user, for example a fixed typo or a colour change to improve readability. Note that security bug fixes should result in a new major release (if really serious) or at least a minor release. This will tell the user that it's probably best to upgrade.
* Libraries
    * Major releases mean breaking changes in your public API, for example a removed method or a changed return type of a method. For a user of your library, to upgrade to a new major release typically has to involve changes to client code.
    * Minor releases mean non-breaking changes, for example added classes and methods. For a user of your library, to upgrade to a new minor release should never require changes to client code.
    * Fixes mean bug fixes, other changes to your private API or internal changes to methods that don't affect the public API. Note that security bug fixes should result in a new major release (if really serious) or at least a minor release. This will tell the user that it's probably best to upgrade.

#### Build the project

Depending on the programming language and environment used, the build process might vary. You may be using Ant, Gradle, Maven or something else. The end result may be a JAR file, and EXE file, a WAR file or something else. Regardless, there are build versions that every release must have. Those are described in the following bullet list.

* Runnable executable or library with compiled code; should contain:
    * the executable file(s) needed to run the application; or compiled code packaged in a DLL, JAR etc.
    * any external configuration files, databases or non-compiled assets needed to run the application (if applicable)
    * readme file(s)
    * license file(s)
    * changelog
    * user manual (if applicable)
* Source code; should contain:
    * all source code files
    * configuration files and assets/resources
    * readme file(s)
    * license file(s)
    * contributing guidelines
    * changelog
    * build files for all build versions
* Documentation files; should contain:
    * documentation generated from the language appropriate tool, for example *javadoc* for Java and *doxygen* for C

All build scripts shall be committed into version control. For more details on how to make these builds, please refer to the manual of respective build tool. It's good to follow the naming conventions of these tools, as well.

### Ending the project
Normally, a programming project never ends. However, if you do want to end a project for whatever reason, you should tell people about that.

Write something like this near the top in the `README.md` file:

```
This project was officially ended 2021-03-27. Therefore, do not expect further 
development. Feel free to clone this repository to continue working on the 
project yourself.
```

It would also be a good idea to [archive the Github repo](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/archiving-repositories). That will create a clear signal that no more work is expected to be made to the project.
