# Milestone release

## Release branch naming
Release branches should be named the same as their corresponding milestone. For 
example, if the milestone is named `1.7.4`, the release branch should be named 
`release/1.7.4`.

## Build project

## Create Github release
Releases on Github provide a way to store binaries, documentation and source. 
Each milestone should have its own release. Here's how you create one:

1. On the Github repository front page, press the *Code* tab. It may be 
selected by default.
1. Press the button *x releases* (where x is the number of releases the 
repository has so far).
1. Press either the button *Create a new release* (if there are no previous 
releases) or *Draft a new release* (if there is at least one previous release).
1. For the *Tag version*, write the same name as the tag you created, for 
example `v1.7.4`.
1. In the dropdown list *Target*, choose the `master` branch.
1. Write the same in *Release title* as in *Tag version*.
1. Write release notes in the text box *Describe this release*. This should be 
a more user-friendly version of the `CHANGELOG.md` file.
1. *Attach* four files:
    * runnable executable or library with compiled code
    * source code without tests
    * source code including tests
    * generated documentation files
1. Leave the checkbox regarding pre-release empty. I don't really use 
pre-releases, but if this release really is one, go for it and check the box.
1. Press the *Publish release* button. You can also save a draft by pressing 
the *Save draft* button.
