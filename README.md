# Olivertwistor Project Model
This is my project model that I'm using with all my programming projects. It includes both instructions and templates.

* [Installation][1]
* [Usage](#usage)
* [Licenses](#licenses)
* [Project instructions](#project-instructions)
    * [Create a new repository](#create-a-new-repository)
    * [Add basic documentation][5]
    * [Create a work breakdown structure](#create-a-work-breakdown-structure)
        * [GitHub issues][6]
    * [Create a network diagram](#create-a-network-diagram)
    * [Work on issues](#work-on-issues)
        * [Branching](#branching)
        * [Testing](#testing)
        * [Documentation][7]
        * [Closing an issue](#closing-an-issue)
    * [Create a release](#create-a-release)
        * [Release schedule][12]
        * [Naming releases][11]
        * [Build the project][8]
    * [End the project](#end-the-project)

## Installation
You can either read all the documents in this repository [online on Github](https://github.com/olivertwistor/olivertwistor-project-model) or [download them for offline use](https://github.com/olivertwistor/olivertwistor-project-model/releases).

## Usage
Follow the section [Installation][1]. If you're using this model as a template for your own projects, feel free to skip any steps that doesn't fit your particular project.

## Licenses
The files in this repository are licensed under a [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) license. For detailed license terms, please read [LICENSE](LICENSE).

## Project instructions
In this section, I will describe the steps to take for a project, from start to finish. Try to follow each step in the order they are written, but don't be afraid to go back to previous steps if you need to add or change something. After all, software development is an iterative and incremental process.

### Create a new repository

These instructions presume that you already have a Github account and are logged in.

1. Go to https://github.com/new
1. Choose a *Repository name*.
1. Write a short *Description* of what the project is about.
1. Choose between making the repository *Public* or *Private*. Public repositories are to be preferred since making it open source gives back to the community. For client work and the like, choose *Private*.
1. Press the button *Create repository*.

### Add basic documentation

The repository should have the following repository documentation, placed in the root of the repository:

* `README.md` ([template](templates/template-readme.md "README.md template"))
* `LICENSE` ([template](templates/template-license.md "LICENSE template"))
* `CONTRIBUTING.md` ([template](templates/template-contributing.md "CONTRIBUTING.md template"))
* `CHANGELOG.md` ([template](templates/template-changelog.md "CHANGELOG.md license"))

### Create a work breakdown structure

In a work breakdown structure (WBS), the goal is to capture the totality of tasks needed for the project to be completed. This can be difficult to do, especially in software development where there are so many unknowns in the beginning. Don't worry if you won't capture all tasks in one go. Just try to capture as many tasks as possible; you can always return to this step later.

[GitHub issues][6] is the place to store the WBS. One issue per task. For now, the order of the tasks aren't important, we'll cover that in the next section when we'll make a network diagram. Just focus on capturing as many tasks as possible. In order to group things together, for example all UI tasks or tasks belonging to a module or part of your project, feel free to create GitHub labels for each group and attach the appropriate ones to your created issues. For each issue, try to decide the importance or priority according to the following table:

| Importance  | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| must-have   | Tasks that are absolutely necessary for the project to work as intended. Think of this importance as that you would have a minimum viable product when all must-have tasks are complete. |
| should-have | Tasks that aren't necessary to create a minimum viable product, but still would greatly enhanced the user experience. |
| could-have  | Tasks of lower importance. Think quality of life, or that extra touch that is nice to have, but nothing that should impede the release of the project if it's not included. |

Add these importance levels as GitHub labels as well. If you're unsure which level to choose for a specific task, leave it for now. You can always come back to it later.

The following table shows an example of a (partial) WBS for a calculator app:

| Issue ID | Description                                | Modules | Importance  |
| :------: | :----------------------------------------- | :------ | :---------- |
|    1     | Design the buttons                         | ui      | must-have   |
|    2     | Lay out all the UI components              | ui      | must-have   |
|    3     | Write help text                            | ui      | should-have |
|    4     | Make all strings translatable              | ui      | could-have  |
|    5     | Make all numbers locale-aware              | ui      | could-have  |
|    6     | Make the app fully keyboard accessible     | ui      | should-have |
|    7     | Define basic arithmetic                    | math    | must-have   |
|    8     | Define statistical functions               | math    | should-have |
|    9     | Enable exporting calculations to text file | io      | could-have  |

Some of these tasks probably could be broken down further, depending on how granular you want your workflow to be. While working, if you discover that a particular task should have been broken down into subtasks, do the following:

1. Add the subtasks as GitHub issues.
1. If appropriate, label the subtasks with the "parent", like so: `math/basic-arithmetic`, if breaking down issue #7 in the preceding table.
1. Close the "parent" GitHub issue.

Also, note that deciding which importance a particular task should get is subjective and depends on what you find more important than other things. In my calculator app example, I've decided that's keyboard accessibility is more important than internationalisation and localisation. My motivation for that is that a user who can't use a mouse would be completely shut out from using the app if the app isn't keyboard accessible, while a user whose native language differs from the app's original language could possibly use a dictionary if need be. The point is that while lack of internationalisation and localisation can make the experience worse for a user, it doesn't *preclude* the user from using the app.

#### GitHub issues

To create GitHub issues based on the task from the WBS, please do the following:

1. On the repository front page, press the *Issues* tab.
1. Press the *New issue* button.
1. Write a short but descriptive *Title*. Example: `Make all strings translatable`.
1. If you want to write more than just that short description, feel free to write it in the *Leave a comment* text box. Here you can write implementation details if you want, or perhaps argue for why this issue was created.
1. Assign a user by pressing the cogwheel besides *Assignee*. This can be altered later, so if you're not sure to whom to assign this issue, it's better to leave it empty for now.
1. Press the cogwheel besides *Labels* and choose all labels that apply. For our calculator app example, appropriate labels would be `ui` and `should-have`. Since it is an enhancement, it should probably also be labelled with `enhancement`. However, neither `ui` nor `enhancement` is mandatory. The important thing here is the importance label (`should-have`).
1. Leave both *Project* and *Milestone* empty. In this model, I'm not using GitHub projects or milestones, but if you do, feel free to select appropriate values here.
1. Press the *Submit new issue* button.

### Create a network diagram

With the work breakdown structure in place, and GitHub issues created, it's now time to create a network diagram. In this step we'll define an order to all tasks, as well their dependency relationships. Some tasks may be quite independent and could be worked on whenever and in parallel with other tasks, but most tasks are either dependent on the completion of other tasks or have dependent tasks themselves.

A network diagram can either be created as a mind map or a table. I'll show an example of the latter next. I'm using the same calculator app example as in the previous section. Note that this is the same table as in the WBS section, with the *Modules* heading removed (for the sake of readability) and dependencies added.

| Issue ID | Description                                | Importance  | Depends upon |
| :------: | :----------------------------------------- | :---------- | :----------: |
|    1     | Design the buttons.                        | must-have   |              |
|    2     | Lay out all the UI components.             | must-have   |              |
|    3     | Write help text.                           | should-have |              |
|    4     | Make all strings translatable.             | could-have  |      3       |
|    5     | Make all numbers locale-aware.             | could-have  |     1, 2     |
|    6     | Make the app fully keyboard accessible.    | should-have |      2       |
|    7     | Define basic arithmetic.                   | must-have   |              |
|    8     | Define statistical functions.              | should-have |      7       |
|    9     | Enable exporting calculation to text file. | could-have  |      7       |

As you can see, it's possible to have both one-to-many dependencies and many-to-one dependencies. For example, when you're finished with issue #2, you may proceed with issue #6, but not issue #5 before you're also finished with issue #1. Unfortunately, GitHub doesn't provide a way to express these kinds of relationships. Apart from managing a network diagram yourself, the only thing that GitHub can help with regarding this is milestones. We will however not use milestones in this model.

Now, we need to reorder the tasks in such a way that the most important tasks get done first, without breaking any dependencies. You can see the results of that in the following table:

| Issue ID | Description                                | Importance  | Depends upon |
| :------: | :----------------------------------------- | :---------- | :----------: |
|    1     | Design the buttons                         | must-have   |              |
|    2     | Lay out all the UI components              | must-have   |              |
|    7     | Define basic arithematic                   | must-have   |              |
|    3     | Write help text                            | should-have |              |
|    6     | Make the app fully keyboard accessible     | should-have |      2       |
|    8     | Define statistical functions               | should-have |      7       |
|    4     | Make all strings translatable              | could-have  |      3       |
|    5     | Make all numbers locale-aware              | could-have  |     1, 2     |
|    9     | Enable exporting calculations to text file | could-have  |      7       |

 

Check in the network diagram file(s) into version control under the folder `project-files`. The file name(s) should begin with `network-`.

### Work on issues

Whenever you are ready to work on an issue, take a look at the closest milestone that's still open. In there, pick an issue that either is assigned to you or is yet unassigned. Please take care to not choose an issue which is dependent upon one or more open issues (see the network diagram). If that's the case, you should work on those issues first. Also, if your chosen issue is unassigned, go assigned it to yourself (as described in the previous section, [Create GitHub issues][6].

#### Branching

All my projects follow the same branching model, [Vincent Driessen's branching model][2]. To learn more about the basics of Git branches, I refer you to the [Git website][3].

The basics of the branching model is that released code is on the `master` branch, tested but not released code on `develop` and each issue on its own `feature/` or `hotfix/` branch. Releases are on a `release/` branch until they are fully released.

Let's say you have decided to work on the issue *Make all strings translatable* (issue #4 in the network diagram). You have assigned yourself to the issue and are about to start working. The first thing you should do is to create a new feature branch. That should include the GitHub issue number, a shortened version of the issue name, and if you're not the only developer, your initials or something else identifying that it is *your* branch. Examples (assume that my initials are "jn"):

* `4-translatable-strings`; or
* `4-translatable-strings-jn`

It's strictly not necessary to include the shortened version of the issue name for uniqueness' sake, but I find it easier to remember what the branch is about than just having the issue number (and the initials).

While working on your issue, commit often so each commit won't have too many code changes. That way, it will be easy for you and others to see what's done and if something went wrong, where. Don't be afraid to push your changes to the remote repository, either. That way, other contributors and even visitors to your project's GitHub page can see your progress.

#### Testing

Testing is a good thing. It should be done wherever and whenever feasible. I'm not very strict about it, though. Sergey Kolodiy have written an excellent [article about unit testing][4].

Each project should detail the testing frameworks in use, in their respective `README.md` file. Test code should be committed to the Git repository so other contributors can benefit from it.

#### Documentation

Documentation is very important, both for your own sake and for your fellow contributors. When working with others or when I'm reviewing other people's code, I often find myself having to closely study the code due to lack of documentation. Ideally, you should be able to get a grasp of what a class or interface, a method or function, or a chunk of code does by only looking at the documentation instead of having to delve into the code.

On top of documenting the code, there is need for documentation outside of the code as well. Please refer to the section [Add basic documentation][5] for templates for that.

#### Closing an issue

When you are done working with an issue, it's time to close it on GitHub. But before you do that, follow this checklist:

1. Make sure that every test passes, and that your code hasn't broken anything else in the code.
1. Update `CHANGELOG.md` with the changes you've made to the project with this issue.
1. If applicable, update `README.md` with more information about installation and usage. Remember to update the license information as well, if you have made use of a new library for this issue.
1. Commit and push the feature branch one final time.
1. Try to merge your feature branch with the `develop` branch.
1. If there are no merge conflicts, proceed to the next step. Otherwise, read on:
    1. Resolve all merge conflicts. If you're unsure of whose code is correct, yours or that of the contributor who last pushed to `develop`, contact them to discuss before going further.
    1. Make sure that every test passes, again, and that your merge hasn't broken anything else in the code.
    1. Commit and push the `develop` branch.
1. Close the GitHub issue. You may write a comment about it if you want, but that's not mandatory. Usually I write "Done." or something similar to denote that I haven't just closed the issue for another reason, for example if the issue is no longer applicable.

### Create a release

When [it's time to make a release][12], please follow these steps:

1. From the `develop` branch, create a new release branch with a [name that reflects the amount of completed work][11], based on Semantic Versioning. For example `releases/1.1.0`.
1. Make sure that every test passes.
1. Make sure that `CHANGELOG.md` and `README.md` properly reflect the state of the project.
1. Make sure that the code doesn't lack [documentation][7].
1. [Make builds of the project][8].
1. [Create a new GitHub release][9] and attach all builds made in the previous step.
1. Merge the release branch with the branches `master` and `develop`.
1. Delete all the feature branches created for this release, as well as the release branch.

#### Release schedule

Releases should be made in set intervals of time, such as monthly, bi-monthly or quarterly. At the beginning of each interval, you will start working on issues in the order set by your network diagram. At the end of each interval, you will take stock of all the work you have done, and create a release with the proper version number. How to go decide on the proper version number, please read the next section.

By doing releases this way, one release may involve huge improvements, while another may involve only tiny ones. It all depends on how much you'll get done in one interval of time. This makes the releases consistent regarding time, but inconsistent when it comes to feature scope.

However, serious bugs and more importantly, security patches should be released immediately when fixed.

#### Naming releases

Releases can be found at the GitHub repo URL appended with `/releases`, for example [Olivertwistor Project Model's releases](https://github.com/olivertwistor/olivertwistor-project-model/releases). They should share names and follow [Semantic Versioning 2.0.0](https://semver.org/). The naming pattern is described next.

Semantic Versioning dictates that version numbers follow a specific pattern: `MAJOR.MINOR.FIX`. A *3.1.4* version number means that it's the third major release of this project, the second minor release within that major release (the first `MINOR` is always a zero), and the fifth fix within that minor release (the first `FIX` is always a zero). You may use the following list to determine whether a particular milestone constitutes a `MAJOR`, `MINOR` or `FIX` version.

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

It would also be a good idea to [archive the Github repo][10]. That will create a clear signal that no more work is expected to be made to the project.

[1]: #installation
[2]: https://nvie.com/posts/a-successful-git-branching-model/
[3]: https://git-scm.com/
[4]: https://www.toptal.com/qa/how-to-write-testable-code-and-why-it-matters
[5]: #add-basic-documentation
[6]: #github-issues
[7]: #documentation
[8]: #build-the-project
[9]: https://docs.github.com/en/github/administering-a-repository/managing-releases-in-a-repository#creating-a-release
[10]: https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/archiving-repositories
[11]: #naming-releases