# Olivertwistor Project Model
This is my project model that I'm using with all my programming projects. It includes both instructions and templates.

* [Installation][27]
* [Usage](#usage)
* [Licenses](#licenses)
* [Project instructions][1]

## Installation
You can either read all the documents in this repository [online on Github][2] or [download them for offline use][3].

## Usage
Follow the section [Installation][27]. If you're using this model as a template for your own projects, feel free to skip any steps that doesn't fit your particular project.

## Licenses
The files in this repository are licensed under a [Creative Commons Attribution 4.0 International][28] license. For detailed license terms, please read [LICENSE][23].

## Project instructions
For every project, go through the following list. Many of the steps are intertwined and meant to be iterated over several times. Also, don't be afraid to go back to previous steps if you need to change or add something. For example, if you are working on issues (step 8) and you discover that you have to add things to the WBS, go back to step 3 and add them, then make the necessary adjusments in steps 4 through 7 before resuming your work at step 8.

Each of these list items is described in further detail in the subsequent sections.

1. [Create a new GitHub repository.][4]
1. [Add the basic repository documents.][5]
1. [Create a work breakdown structure (WBS).][10]
1. Create a network diagram based on the WBS.
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

* `README.md` ([template][6])
* `LICENSE` ([template][7])
* `CONTRIBUTING.md` ([template][8])
* `CHANGELOG.md` ([template][9])

### Create a work breakdown structure

In a work breakdown structure (WBS), the goal is to capture the totality of tasks needed for the project to be completed.


[1]: #project-instructions
[2]: https://github.com/olivertwistor/olivertwistor-project-model
[3]: https://github.com/olivertwistor/olivertwistor-project-model/releases
[4]: #create-a-new-repository
[5]: #add-basic-documentation
[6]: templates/template-readme.md "README.md template"
[7]: templates/template-license.md "LICENSE template"
[8]: templates/template-contributing.md "CONTRIBUTING.md template"
[9]: templates/template-changelog.md "CHANGELOG template"
[10]: #create-a-work-breakdown-structure
[23]: LICENSE
[28]: https://creativecommons.org/licenses/by/4.0/
