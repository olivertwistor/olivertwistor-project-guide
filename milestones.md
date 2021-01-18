# Milestones

Milestones can be found at the GitHub repo URL appended with `/milestones`, for example [Olivertwistor Project Model's milestones][1]. They can also be created directly from the issue detail's page.

Each milestone represents a release, and should contain all issues that need to be resolved for that release. Since milestones represent releases, they should share names. As described in the [documentation about releases][2], milestones should follow [Semantic Versioning 2.0.0][3].

## Which version number should be next?

Semantic Versioning dictates that version numbers follow a specific pattern: `MAJOR.MINOR.FIX`

A *3.1.4* version number means that it's the third major release of this project, the second minor release within that major release, and the fifth fix within that minor release.

### Applications

* Major releases mean big changes or additions in functionality, resulting in brand new ways of using the application.
* Minor releases mean smaller changes or additions in functionality, for example that the user can save a file in PDF format in addition to TXT, as was the case previously.
* Fixes mean bug fixes or other very small things that don't involve a change in functionality. This can  be things both visible and invisible to the user, for example a fixed typo or a colour change to improve readability. Note that security bug fixes should result in a new major release (if really serious) or at least a minor release. This will tell the user that it's probably best to upgrade.

### Libraries

* Major releases mean breaking changes in your public API, for example a removed method or a changed return type of a method. For a user of your library, to upgrade to a new major release typically has to involve changes to client code.
* Minor releases mean non-breaking changes, for example added classes and methods. For a user of your library, to upgrade to a new minor release should never require changes to client code.
* Fixes mean bug fixes, other changes to your private API or internal changes to methods that don't affect the public API. Note that security bug fixes should result in a new major release (if really serious) or at least a minor release. This will tell the user that it's probably best to upgrade.

[1]: https://github.com/olivertwistor/olivertwistor-project-model/milestones
[2]: branching.md#release
[3]: https://semver.org/