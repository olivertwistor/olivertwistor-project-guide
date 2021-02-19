# Olivertwistor Project Model
This is my project model that I'm using with all my programming projects. It includes both instructions and templates.

* [Installation][1]
* [Usage](#usage)
* [Licenses](#licenses)
* [Project instructions](#project-instructions)

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

In a work breakdown structure (WBS), the goal is to capture the totality of tasks needed for the project to be completed. This can be difficult to do, especially in software development where there are so many unknowns in the beginning. Don't worry that you might not capture all tasks in one go. Just try to capture as many tasks as possible; you can always return to this step later.

It's a good idea to store the WBS as a mind map or a nested list. That way you can have multiple levels of granularity over your tasks, in order to have better overview of all tasks. Neither the order of the tasks nor their priority are important (you will deal with that at later steps). Try to make each task a manageable size, like four to eight hours. If it would be larger, it's probably more suitable to be a work package (closer to the middle in the mind map).

![An example of a WBS as a mind map](examples/wbs-example.png)

This image shows a (partial) WBS of a calculator app. Note that only the outermost nodes in the map are considered to be tasks. All other are work packages &mdash; groups of tasks that are connected in some way. 

The tasks in this example are:

* Design the buttons
* Lay out all the UI components
* Write help text
* Make all strings translatable
* Make all numbers locale-aware
* Make the app fully keyboard accessible
* Define basic arithmetic
* Define statistical functions
* Enable exporting calculations to text file.

The same WBS presented in a nested list would look like this:

1. Create the UI
    1. Design the buttons.
    1. Lay out all the UI components.
    1. Write help text.
    1. Do localization.
        1. Make all strings translatable.
        1. Make all numbers locale-aware.
    1. Make the app fully keyboard accessible.
1. Define the mathematical operations.
    1. Define basic arithmetic.
    1. Define statistical functions.
1. Enable exporting calculations to text file.

In my example, the task *Enable exporting calculations to text file* could probably be broken down further and thus would be more suited as a work package. While working with your project, you will undoubtedly discover things like this. When it happens, you can go back back to this step and add to the WBS.

Check in the work breakdown structure file(s) into version control under the folder `project-files`. The file name(s) should begin with `wbs-`.

### Create a network diagram

With the work breakdown structure in place, it's now time to create a network diagram. This is the step where you define an order to all tasks, as well their dependency relationships. Some tasks may be quite independent and could be worked on whenever and in parallel with other tasks, but most tasks are dependent on the completion of other tasks or have themselves dependent tasks.

A network diagram can either be created as a mind map or a table. I'll show an example of a mind map first. I'll use the same calculator app example as in the previous section.

![An example of a network diagram as a mind map](examples/network-example.png)

The same network diagram presented in a table would look like this:

| ID    | Name                                       | Depends upon              |
| ----- | ------------------------------------------ | ------------------------- |
|       | *Project start*                            |                           |
| 1.1   | Design the buttons.                        |                           |
| 1.2   | Lay out all the UI components.             |                           |
| 1.3   | Write help text.                           |                           |
| 1.4.1 | Make all strings translatable.             | 1.3                       |
| 1.4.2 | Make all numbers locale-aware.             | 1.1, 1.2                  |
| 1.5   | Make the app fully keyboard accessible.    | 1.2                       |
| 2.1   | Define basic arithmetic.                   |                           |
| 2.2   | Define statistical functions.              | 2.1                       |
| 3     | Enable exporting calculation to text file. | 2.1                       |
|       | *Project end*                              | 1.4.1, 1.4.2, 1.5, 2.2, 3 |

Note that the ID's correspond to the tasks in the nested list from the previous section. Also, note that I added a *Project start* and a *Project end*. Obviously, a work breakdown structure and network diagram is much more detailed than this in a real-life project.

As you can see, it's possible to have both one-to-many dependencies and many-to-one dependencies. For example, when you're finished with task 1.2, you may proceed with task 1.5, but not task 1.4.2 before you're also finished with task 1.1.

Unfortunately, GitHub doesn't provide a way to express these kinds of relationships. Apart from managing a network diagram yourself, the only thing that GitHub can help with regarding this is milestones. We will discuss those in the next section.

Check in the network diagram file(s) into version control under the folder `project-files`. The file name(s) should begin with `network-`.

### Add milestones

Milestones are points during the development when you have something that is deliverable, for example when a feature is implemented. Think of milestones as the big steps you need to take in order to finish the project, and tasks as the small steps leading up to each milestone. You should start with the network diagram and insert milestones at appropriate places. For example:

![An example of a network diagram with milestones added.](examples/network-with-milestones-example.png)

Note that to increase readability in the image, *Milestone 3* leads to a task to its southwest. Milestones are coloured yellow and tasks coloured light blue. The same diagram can be presented as a table, as follows:

| ID     | Name                                        | Depends upon        |
| ------ | ------------------------------------------- | ------------------- |
|        | *Project start*                             |                     |
| 1.1    | Design the buttons.                         |                     |
| 1.2    | Lay out all the UI components.              |                     |
| 2.1    | Design basic arithmetic.                    |                     |
| *MS 1* | *Milestone 1*                               | *1.1, 1.2, 2.1*     |
| 1.3    | Write help text.                            |                     |
| *MS 2* | *Milestone 2*                               | *1.3*               |
| 1.4.1  | Make all strings translatable.              | 1.3                 |
| 1.4.2  | Make all numbers locale-aware.              | 1.1, 1.2            |
| 1.5    | Make the app fully keyboard accessible.     | 1.2                 |
| *MS 3* | *Milestone 3*                               | *1.4.1, 1.4.2, 1.5* |
| 2.2    | Define statistical functions                | 2.1                 |
| *MS 4* | Milestone 4                                 | 2.2                 |
| 3      | Enable exporting calculations to text file. | 2.1                 |
|        | *Project end*                               |                     |

In this example with the calculator app, we have defined four milestones (if we don't include the project end). This means that we can deliver five consecutive versions of the app. The first version with the ability to do basic arithemetic, and with the buttons and UI elements laid out. The second version have a help text. The third version includes accessibility enhancements. The fourth version adds statistical functions to the calculator. The fifth and final version enables the user to export their calculations to a text file. By doing things this way, the users can quickly begin using your app, already after three of the nine tasks in total.

In which order you decide to do tasks and milestones depends on how you prioritize functionality. That the first milestone in my example should come first is probably not controversial &mdash; it's pointless to do anything else before laying the foundation for the app to even be operable. However, milestones 2 through 4 can be debated. Is accessibility more important than a help text? Is providing statistical functions and export capabilities more important than accessibility? It depends on your user base. If your user base comprises of statisticians who speak the same language as you, and are capable of using a mouse, then it would make much more sense to move *Milestone 3* to before *Milestone 2* (and leave everything else unchanged). Please note that we couldn't have switched places of *Milestone 1* and *Milestone 2*, because task 1.4.1 in *Milestone 2* depends on task 1.3 in *Milestone 1*.

#### Milestones in GitHub

Milestones can be found at the GitHub repo URL appended with `/milestones`, for example [Olivertwistor Project Model's milestones](https://github.com/olivertwistor/olivertwistor-project-model/milestones). They can also be created directly from the issue detail's page. 

Each milestone represents a release, and should contain all issues that need to be resolved for that release. Since milestones represent releases, they should share names and follow [Semantic Versioning 2.0.0](https://semver.org/). The naming pattern is described next.

Semantic Versioning dictates that version numbers follow a specific pattern: `MAJOR.MINOR.FIX`. A *3.1.4* version number means that it's the third major release of this project, the second minor release within that major release, and the fifth fix within that minor release. You may use the following list to determine whether a particular milestone constitutes a `MAJOR`, `MINOR` or `FIX` version.

* Applications
    * Major releases mean big changes or additions in functionality, resulting in brand new ways of using the application.
    * Minor releases mean smaller changes or additions in functionality, for example that the user can save a file in PDF format in addition to TXT, as was the case previously.
    * Fixes mean bug fixes or other very small things that don't involve a change in functionality. This can be things both visible and invisible to the user, for example a fixed typo or a colour change to improve readability. Note that security bug fixes should result in a new major release (if really serious) or at least a minor release. This will tell the user that it's probably best to upgrade.
* Libraries

    * Major releases mean breaking changes in your public API, for example a removed method or a changed return type of a method. For a user of your library, to upgrade to a new major release typically has to involve changes to client code.
    * Minor releases mean non-breaking changes, for example added classes and methods. For a user of your library, to upgrade to a new minor release should never require changes to client code.
    * Fixes mean bug fixes, other changes to your private API or internal changes to methods that don't affect the public API. Note that security bug fixes should result in a new major release (if really serious) or at least a minor release. This will tell the user that it's probably best to upgrade.

### Create GitHub issues

x



### Work on issues

x

### Create a release

x



[1]: #installation