# Milestone plan
In this phase, it's time for making plans for the next milestone(s).

## Work breakdown structure
In a work breakdown structure (WBS), you try to divide the whole project into 
as small as possible work units. For example, if you're throwing a birthday 
party, one work unit may be *Order the cake*. A work unit should be the 
smallest thing you can do without having too much dependence on other things. 
If we take the birthday party example again, having a work unit be *Dial the 
phone number to the bakery* would be silly. That's way too small.

In a WBS, order of the work units is not important. It's enough to concentrate 
on trying to create as full a picture of the project as possible. When the WBS 
is done, ideally it should describe every single piece of work needed to 
complete the project. In an agile development project, this is rarely if ever 
possible. Instead, we should focus on an iterative WBS process, where we'll 
create a WBS for each milestone (or preferrably several). Remember, a milestone 
in this project plan is a release or deliverable.

The WBS may be written as an ordinary text file or Markdown file and committed 
to the repository, in the project file folder.

# Create issue
Each work unit in the work breakdown structure should have its own Github 
issue. To create a new issue, follow these instructions:

1. On the repository front page, press the *Issues* tab.
1. Press the green *New issue* button.
1. Write a short but descriptive *Title*. Example: `Make all buttons have 
yellow backgrounds and pink text colour`.
1. If you want to write more than just that short description, feel free to 
write it in the *Leave a comment* text box. Here you can write implementation 
details if you want, or perhaps argue for why this issue was created.
1. Assign a user by pressing the cogwheel besides *Assignees*. This can always 
be altered later, so if you're not sure about to whom to assign this issue, 
it's better to leave it empty for now.
1. Labels should at this stage have been created. If they haven't, please 
follow the [instructions on setting up basic labels][1] before continuing. When 
there are basic labels setup, press the cogwheel besides *Labels* and choose 
all labels that apply.
1. Leave both *Project* and *Milestone* be for now.
1. Press the *Submit new issue* button.
1. Repeat until there are no more work units without a Github issue left.

## Create milestone
To create a milestone and assign issues to it, follow these steps:

1. On the *Issues* tab on your project's repository page, press the button 
*Milestones*.
1. Press the button *New milestone*.
1. Give the milestone a *Title*. It doesn't have to be the same as the version 
number, but I recommend that.
1. Leave the *Due date* empty.
1. Write a description if you want. This can include the main changes that come 
with this release. You can just leave it empty.
1. Press the button *Create milestone*.

Now it's time to assign issues to the newly created milestone. Remember that in 
this project model, a milestone represents the changes necessary to go from one 
stable functioning state to another stable functioning state. A milestone 
should therefore include all the issues that are necessary to go between two 
functioning states. It could be as little as one issue, but it can be much 
larger. It depends on the size of the issues and also the size of the 
milestones/releases. Try to keep each milestone small, although having a 
milestone for only one issue might be a bit too small. :smile:

1. Go back to the *Issues* tab.
1. For each of the issues that should be assigned to the milestone:
    1. Press its name so you see the issue details.
    1. Press the cogwheel besides *Milestone*. Choose the desired milestone.

[1]: repo-setup.md#setup-basic-labels