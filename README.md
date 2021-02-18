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
For every project, go through the following list. Many of the steps are intertwined and meant to be iterated over several times. Also, don't be afraid to go back to previous steps if you need to change or add something. For example, if you are working on issues (step 8) and you discover that you have to add things to the WBS, go back to step 3 and add them, then make the necessary adjusments in steps 4 through 7 before resuming your work at step 8.

Each of these list items is described in further detail in the subsequent sections.

1. [Create a new GitHub repository.](#create-a-new-repository)
1. [Add the basic repository documents.](#add-basic-documentation)
1. [Create a work breakdown structure (WBS).](#create-a-work-breakdown-structure)
1. [Create a network diagram](#create-a-network-diagram) based on the WBS.
1. Create GitHub issues based on the WBS.
1. Add appropriate milestones based on the network diagram.
1. Assign all GitHub issues to their respective milestone based on the network diagram.
1. Work on issues belonging to the first unreleased milestone.
1. Create a release based on the milestone in step 8.

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

It's a good idea to store the WBS as a mind map. That way you can have multiple levels of granularity over your tasks, in order to have better overview of all tasks. The order of the tasks are not important (you will order them at a later step). Try to make each task a manageable size, like four to eight hours. If it would be larger, it's probably more suitable to be a work package (closer to the middle in the mind map).

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

### Create a network diagram



[1]: #installation