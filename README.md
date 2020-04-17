# Olivertwistor Project Guide

* [Background](#background)
* [Purpose](#purpose)
* [Goal](#goal)
* [Stakeholders](#stakeholders)
* [Usage](#usage)
* [Project instructions][3]
    * [Repository setup][8]
    * [Project plan][10]
    * [Milestone plan][11]
    * [Milestone execution][12]
    * [Milestone release][13]
    * [Project end][14]
* [Licensing](#licensing)
* [How to contribute](#how-to-contribute)
* [Versioning](#versioning)

## Background
When starting a new project, whether it is software development or anything 
else, it helps to have a structured approach. Otherwise it's easy to lose track 
of what to do, and you have to create ad-hoc solutions every time. This project 
model is supposed to be that structured approach.

## Purpose
The purpose of this project model is to help me, others who might collaborate 
with me on my projects and other people who want to build upon this model for 
their own projects. This model is created with software development on Github 
in mind, but with some minor changes, it would work for other project types as 
well.

## Goal
The goal is to create a project model that I can use for all my projects, 
public and private.

## Stakeholders
The people interested in this project is mainly me, but also others who may be 
interested in using this model for themselves.

## Usage
If you're using this model as a template for your own projects, feel free to 
skip any steps that doesn't fit your particular project.

You can either read all the documents in this repository [online on Github][1] 
or [download them for offline use][2].

## Project instructions
For every project, go through each of the following phases: 
[repository setup][8], [project plan][10], [milestone plan][11], 
[milestone execution][12], [milestone release][13] and [project end][14]. These 
phases are often intertwined and you have to iterate over them many times, 
especially the milestone phases. This outlines the general order; don't be 
afraid to go back to a previous phase if you need to change something.

The steps [milestone plan][11], [milestone execution][12] and 
[milestone release][13] are designed to be iterated over as long as there are 
open issues or new development ideas.

### Repository setup
1. [Create a new Github repository][15].
1. [Enable issues](lifecycle/repo-setup.md#enable-issues) in Settings.
1. Remove any default labels and [add the following labels][16]:
    * `priority: must`
    * `priority: should`
    * `priority: could`
    * `priority: would`

### Project plan
When the repository has been properly setup, it's time to start planning the 
project as a whole.

1. In the file `README.md`, write the following:
    1. Background &mdash; What is the context in which the project exist? Are 
    there any competing projects out there?
    1. Purpose &mdash; Why do we need the project? What is the desired 
    long-term outcome?
    1. Goal &mdash; What will the final product or service look like?
    1. Stakeholders &mdash; Who are the users? Are there any regulations that 
    affects the project?
1. Choose an appropriate license and put the details in a file called 
`LICENSE`.

### Milestone plan
In this project model, a milestone is equivalent to a release or deliverable. 
On Github, a milestone consists of a number of issues. Therefore you should 
think of a milestone and the issues therein as what needs to be done to get the 
project from one functioning state (the previous milestone) to another 
functioning state (the next milestone).

1. Create a [work breakdown structure][20] (WBS) in as long a perspective as 
possible.
1. [Create a new Github issue][21] for each work unit and prioritize them.
1. [Create a new Github milestone][22] with the issues that would lead to the 
next functioning state of the project. Give priority to issues with higher 
priority.
1. **Optional**: Create more milestones as in step 3, if you are able to plan 
that far ahead.

### Milestone execution
1. Pick the open milestone with the lowest version number.
1. As long as there are open issues that are either unassigned or assigned to 
you:
    1. Pick an issue that you want to work on, and [assign yourself to it][17]. 
    To simplify things, only assign yourself on unassigned issues.
    1. [Create a new feature branch][18] named with the issue number and maybe 
    a short description. Example: *5-blue-bg*
    1. As long as you're not done with the issue:
        1. Do some work. Commit often.
        1. [Write tests][19] and run them. When they pass, push the branch.
    1. Make sure that everything is [properly documented][23].
    1. Add what you have done in the [changelog][24].
    1. Push the branch a final time.
    1. Try to merge with `develop`.
    1. If there are merge issues:
        1. Resolve them to the best of your abilites. If in doubt, please ask 
        the conflicting code's author.
        1. Run all available tests again. When they pass, push the merge.
    1. Close the issue.

### Milestone release
When all issues in a milestone are closed, it's time to prepare for a new 
release of the project.

1. Pick the milestone with the lowest version number that has all its issues 
completed.
1. Verify that the code related to each issue is pushed to (or merged with) the 
`develop` branch.
1. Create a new [release branch named as the milestone version number][26].
1. [Run all available tests][19] until they pass.
1. Make sure that everything is [properly documented][23].
1. Update `README.md` as necessary, regarding instructions on installation and 
usage.
1. [Create a new Git tag][27] named as the milestone prepended with a *v*. 
Example: `v1.5.2`. Push everything.
1. [Build the project][29] in at least four versions:
    * runnable executable or library with compiled code
    * source code without tests
    * source code including tests
    * generated documentation files
1. Merge the release branch with the `master` and `develop` branches.
1. [Create a new Github release][28] from the created tag. Describe the changes 
made since last release.
1. Delete all the feature, hotfix and release branches that was created for 
this milestone.

### Project end
Normally, programming projects never really end, but in case you want to 
permanently cease development of a project and haven't got anyone else who want 
to take over, you may follow these steps for an orderly end to the project.

1. Update `README.md` [with information that the project has permanently come 
to an end][25] and that visitors to the repository can't expect there to be 
further development. Push the change to the `master` branch.

## Licensing
The files in this repository are licensed under a Creative Commons Attribution 
4.0 International license. For detailed license terms, please read [LICENSE][5].

## How to contribute
If you want to contribute to this project, please read the file 
[CONTRIBUTING.md][4] for details.

## Versioning
This project use [Semantic Versioning 2.0.0][6]. The latest version number and 
all changes to this project can be read in the file [CHANGELOG.md][9].


[1]: https://github.com/olivertwistor/olivertwistor-project-guide
[2]: https://github.com/olivertwistor/olivertwistor-project-guide/releases
[3]: #project-instructions
[4]: CONTRIBUTING.md
[5]: LICENSE
[6]: https://semver.org/
[7]: https://github.com/olivertwistor/olivertwistor-programming-style-guide
[8]: #repository-setup
[9]: CHANGELOG.md
[10]: #project-plan
[11]: #milestone-plan
[12]: #milestone-execution
[13]: #milestone-release
[14]: #project-end
[15]: lifecycle/repo-setup.md#create-a-github-repository
[16]: lifecycle/repo-setup.md#setup-basic-labels
[17]: lifecycle/milestone-execution.md#assign-issues
[18]: lifecycle/milestone-execution.md#branches
[19]: lifecycle/milestone-execution.md#testing
[20]: lifecycle/milestone-plan.md#work-breakdown-structure
[21]: lifecycle/milestone-plan.md#create-issue
[22]: lifecycle/milestone-plan.md#create-milestone
[23]: lifecycle/milestone-execution.md#documentation
[24]: lifecycle/milestone-execution.md#changelog
[25]: lifecycle/project-end.md
[26]: lifecycle/milestone-release.md#release-branch-naming
[27]: https://git-scm.com/book/en/v2/Git-Basics-Tagging
[28]: lifecycle/milestone-release.md#create-github-release
[29]: lifecycle/milestone-release.md#build-project
