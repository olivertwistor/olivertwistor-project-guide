# Branching
My projects all follow the same branching model, in order to make things easy 
for everyone: [Vincent Driessen's branching model][1]. To learn more about the 
basics of Git branches, I refer you to the [Git website][2].

## Release
A branch of this type should be created whenever it's time for a new release of 
the project. It should be created from the `develop` branch. On a release 
branch, only bug fixes and documentation may be added.

Release branches should be named with the version number corresponding to that 
release. For example, `release/1.7.4`.

When all work on the release branch is done, it should be merged with both the 
`master` and `develop` branches.


[1]: https://nvie.com/posts/a-successful-git-branching-model/
[2]: https://git-scm.com/
