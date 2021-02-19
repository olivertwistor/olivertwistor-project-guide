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
|       |                                            |                           |

Note that the ID's correspond to the tasks in the nested list from the previous section. Also, note that I added a *Project start* and a *Project end*. Obviously, a work breakdown structure and network diagram is much more detailed than this in a real-life project.

As you can see, it's possible to have both one-to-many dependencies and many-to-one dependencies. For example, when you're finished with task 1.2, you may proceed with task 1.5, but not task 1.4.2 before you're also finished with task 1.1.

Unfortunately, GitHub doesn't provide a way to express these kinds of relationships. Apart from managing a network diagram yourself, the only thing that GitHub can help with regarding this is milestones. We will discuss those in the next section.

Check in the network diagram file(s) into version control under the folder `project-files`. The file name(s) should begin with `network-`.

### Add milestones

x

### Create GitHub issues

x



### Work on issues

x

### Create a release

x



[1]: #installation