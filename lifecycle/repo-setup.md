# Repository setup
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

## Setup basic labels
Labels can be attached to issues, giving further details on an issue than 
merely its title. Github comes with a set of default labels, which I don't find 
particularly helpful for my own projects.

1. On the repository front page, go to the *Issues* tab.
1. Press the button *Labels*.
1. For every existing label, press the button *Delete*. Choose *OK* in the 
confirmation popup.
1. Press the button *New label*.
1. Enter the following information:
    * *Label name*: `priority: must`
    * *Description*: `This issue must be resolved to even get the project in a 
    functional state at all.`
    * *Color*: `#f99`
1. Press the button *Create label*.
1. Press the button *New label*.
1. Enter the following information:
    * *Label name*: `priority: should`
    * *Description*: `This issue really should be resolved, but leaving it 
    doesn't break the project.`
    * *Color*: `#ff9`
1. Press the button *Create label*.
1. Press the button *New label*.
1. Enter the following information:
    * *Label name*: `priority: could`
    * *Description*: `This issue could be resolved if it doesn't affect 
    anything else negatively and if there is time.`
    * *Color*: `#9f9`
1. Press the button *Create label*.
1. Press the button *New label*.
1. Enter the following information:
    * *Label name*: `priority: would`
    * *Description*: `This issue would be nice if resolved, but it probably 
    will have to wait.`
    * *Color*: `#99f`
    
We have now created four different priority labels, in descending priority order. We will use them at a later stage when planning milestones.