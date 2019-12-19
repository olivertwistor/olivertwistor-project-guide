# Olivertwistor Project Guide
Hello! I am Johan Nilsson a.k.a. Olivertwistor. This is a project model for my 
programming projects. The purpose is twofold:

* to make it easier for me to work with my programming projects
* to help contributors know how to work with my projects

## Table of contents

* [Who is this for?](#who-is-this-for)
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

## Who is this for?
This project model is mainly for me and anyone who is a contributor to any of 
the projects I've created.

It can also be used as a template for your own projects. Feel free to build 
upon this to get a head start.

## Usage
The purpose of this project model is to be of help when working with 
programming projects. The way to use it is to follow the step-by-step 
[instructions defined in this document][3].

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

### Repository setup
1. Create a new Github repository.
1. Enable issues in Settings.
1. Remove any default labels and add the following labels:
    * `priority: must`
    * `priority: should`
    * `priority: could`
    * `priority: wait`

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

1. Create a work breakdown structure (WBS) in as long a perspective as possible.
1. Create a new Github issue for each work package and prioritize them.
1. Create a new Github milestone with the issues that would lead to the next 
functioning state of the project.
1. Optional: Create more milestones as in step 3, if you are able to plan that 
far ahead.

### Milestone execution

### Milestone release

### Project end

## Licensing
The files in this repository is licensed under a Creative Commons Attribution 
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
