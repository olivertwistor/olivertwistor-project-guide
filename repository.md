# Repository
The following instructions are tailored for Git repositories hosted by Github. 
If you're using some other version control system (such as CVS, SVN or 
Mercurial) or if you're using some other platform (such as Bitbucket, GitLab or 
perhaps your own server), some of the instructions won't apply to you. Please 
refer to the manuals for your version control system or platform for specific 
instructions.

## Create a Github repository
These instructions presume that you already have a Github account and are 
logged in.

1. Go to https://github.com/new to create a new repository.
1. Choose a *Repository name*.
1. Write a short *Description* of what the project is about.
1. Choose between making the repository *Public* or *Private*. Public 
repositories are to be preferred since making it open source gives back to the 
community. For client work and the like, choose *Private*.
1. Press the button *Create repository*.

## Enable issues
Issues are a great way for yourself and others to keep track of what needs to 
be done (and what already has been done).

1. On the repository front page, go to the *Settings* tab.
1. Scroll down to *Features*.
1. Check the *Issues* checkbox.

## Labels

GitHub repositories come with nine default labels: *bug*, *documentation*, *duplicate*, *enhancement*, *good first issue*, *help wanted*, *invalid*, *question* and *wontfix*.

I don't use the labels *duplicate*, *good first issue*, *invalid* and *wontfix*, so delete them. Add the following labels instead: *core* and *polish*. Core is for core functionality and is typically of higher importance than polish, which is more for quality of life things such as internationalization and GUI styling &mdash; stuff that makes your application easier to use and more accessible, but they are not strictly necessary to make it functional.

The following table summarizes the labels that every repository should have.

| Label         | Description                                              |
| ------------- | -------------------------------------------------------- |
| bug           | Something isn't working                                  |
| core          | Core functionality                                       |
| documentation | Improvements or addition to documentation                |
| enhancement   | New feature or request                                   |
| help wanted   | Extra attention is needed                                |
| polish        | Quality of life, not strictly necessary but nice to have |
| question      | Further information is requested                         |

Which colour each label has is not defined in this project model. Use your own judgement and preference. Additional labels may be created based on the needs for your particular project.