# Milestone execution
In this phase, it's time to do some actual work done that's not purely 
documentation.

## Assign issues
Issues should be left unassigned until someone is willing to start working on 
them. When you are ready to start working on an issue, you should assign it to 
yourself.

1. Go to the issue list belonging to the milestone you're currently working on.
1. Click on an issue that is unassigned. You can see if it is by the lack of an 
avatar in the `Assignee` column.
1. In the sidebar to the right and at the top is a heading called `Assignees`. 
Either click the link `No one&mdash;assign yourself` or click the little 
cogwheel and select yourself.

## Branches
For the basics about Git branches, I refer you to the [Git website][1].

My projects all follow the same branching model, in order to make things easy 
for everyone: [Vincent Driessen's branching model][2].

## Testing
Testing is a good thing. It should be done wherever and whenever feasible, 
although I'm not religious about it. Sergey Kolodiy have written an excellent 
[article about unit testing][3].

Each project should detail the testing frameworks that should be used, in their 
respective `README.md` file. Test code should be committed to the Git 
repository so other contributors can benefit from it.

## Documentation
All classes, interfaces, methods and functions should be documented using 
whatever format is standard for the programming language in question, for 
example Javadoc for Java. Comments inside of methods and functions are highly 
suggested, particularly for big or complex chunks of code.

## Changelog
The changelog is a file that details all the (significant) changes done to the 
code between releases. More specifically, it details changes to the API. Thus, 
the intended audience is not primarily the end-user, but instead other 
developers.

The changelog should be written to a file called `CHANGELOG.md`, be stored in 
the repository root and follow the same format as [Keep a Changelog][4].

[1]: https://git-scm.com/
[2]: https://nvie.com/posts/a-successful-git-branching-model/
[3]: https://www.toptal.com/qa/how-to-write-testable-code-and-why-it-matters
[4]: https://keepachangelog.com/en/1.0.0/
