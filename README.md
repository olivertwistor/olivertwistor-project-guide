# Olivertwistor Project Model
This is my project model that I'm using with all my programming projects. It 
includes both instructions and templates.

* [Installation][27]
* [Usage](#usage)
* [Licenses](#licenses)
* [Project instructions][1]

## Installation
You can either read all the documents in this repository [online on Github][2] 
or [download them for offline use][3].

## Usage
Follow the section [Installation][27]. If you're using this model as a 
template for your own projects, feel free to skip any steps that doesn't fit 
your particular project.

## Licenses
The files in this repository are licensed under a [Creative Commons 
Attribution 4.0 International][28] license. For detailed license terms, please 
read [LICENSE][23].

## Project instructions
For every project, go through the following list. Many of the steps are 
intertwined and meant to be iterated over several times. Also, don't be afraid 
to go back to previous steps if you need to change something.

1. [Create a new Github repository][4].
1. Enable issues in Settings.
1. Follow the [general readme template][7] as well as any specialized readme 
template. Name that file `README.md` and put in the root of the repo.
1. Follow the [general contributing template][24] as well as any specialized 
contributing template. Name that file `CONTRIBUTING.md` and put in the root of 
the repo.
1. Follow the [general changelog template][25] as well as any specialized 
changelog template. Name that file `CHANGELOG.md` and put in the root of the 
repo.
1. Follow the [general license template][26] as well as any specialized license
template. Name that file `LICENSE` and put in the root of the repo.
1. As long as this project is active:
    1. For each separate feature to implement (or more generally, for each 
    thing to do):
        1. [Create a new Github issue][8] and give it appropriate labels.
    1. As long as there are open issues that are either unassigned or assigned 
    to you:
        1. Pick an issue that you want to work on, and [assign yourself to 
        it][9]. To simplify things, only assign yourself on unassigned issues.
        1. [Create a new feature branch][10] named with the issue number, a 
        short description and your Github username. Example: 
        *5-blue-bg-olivertwistor*. If you're the only developer, you don't have 
        to include your Github username.
        1. As long as you're not done with the issue:
            1. [Write tests][11]. Initially, they will fail.
            1. Do some work. Commit (and push) often.
            1. Verify that the tests pass. If they do, push everything a final 
            time. If they don't, repeat the previous step.
        1. Make sure that everything is [properly documented][12].
        1. Add what you have done in the [changelog][13].
        1. Push the branch a final time.
        1. Try to merge with `develop`.
        1. If there are merge issues:
            1. Resolve them to the best of your abilities. If in doubt, please 
            ask the other developers.
            1. Run all available tests again. When they pass, push the merge.
            1. Close the issue.
        1. If it's [time to make a new release][15], break out of this loop 
        level.
    1. Create a new [release branch named after the next version number][16].
    1. [Run all available tests][11] until they pass.
    1. Make sure that everything is [properly documented][12].
    1. Update `README.md` as necessary, specifically regarding instructions on 
    [installation][17] and [usage][18].
    1. [Create a new Git tag][19] named as the release, prepended with *v*. 
    Example: `v1.5.2`. Push everything.
    1. [Build the project][20] in at least four versions:
        * runnable executable or library with compiled code
        * source code without tests
        * source code including tests
        * generated documentation files
    1. Merge the release branch with the `master` and `develop` branches.
    1. [Create a new Github release][21] from the created tag. Describe the 
    changes made since last release.
    1. Delete all the feature, hotfix and release branches that was created for 
    the release.
1. Update `README.md` [with information that the project has permanently come 
to an end][22] and that visitors to the repository can't expect there to be 
further development. Push the change to the `master` branch.


[1]: #project-instructions
[2]: https://github.com/olivertwistor/olivertwistor-project-model
[3]: https://github.com/olivertwistor/olivertwistor-project-model/releases
[4]: repository.md#create-a-github-repository
[7]: templates/template-readme.md
[8]: issues.md#create-issue
[9]: issues.md#assign-issues
[10]: branching.md
[11]: testing.md
[12]: documentation.md
[13]: documentation.md#changelog
[15]: building.md#release-schedule
[16]: branching.md#release
[17]: readme-instructions.md#installation
[18]: readme-instructions.md#usage
[19]: https://git-scm.com/book/en/v2/Git-Basics-Tagging
[20]: building.md#build-project
[21]: building.md#create-github-release
[22]: project-end.md
[23]: LICENSE
[24]: templates/template-contributing.md
[25]: templates/template-changelog.md
[26]: templates/template-license.md
[27]: #installation
[28]: https://creativecommons.org/licenses/by/4.0/
