Contributing to BTDstudios projects
==========================
**Note:** This document describes the development guidelines for BTDstudios. It may be changed at any time.
Because of that you should refer to the development guidelines when working on any contributions.

BTDstudios is happy that you want to contribute to our projects.
We are usually not very strict with all submitted PRs, 
but there are still some guidelines you can follow to make the approval process go more smoothly:

- **Use the right IDE configuration.** So that the whole code style is similar we use a special IDE configuration in
some places. To apply it in the right way view our 
- **Target the right Java version.** The targeted Java version may change from version / branch to the next one.
- **Use only spaces for indentation.** Our indents are 4-spaces long, and tabs are unacceptable.
- **Follow given style of code.** So that we can accept your contribution in a faster way,
you should follow the given style of code around the position to edit: [Examples](#code-style)
- **Write complete Javadocs.** Do so only for public methods.
Make sure that your `@param` and `@return` fields are not just blank.
- **Don't tag classes with @author.** Some external classes may have this tag, but we are not using it for our projects. 
- **Make sure the code is efficient.** Think about moving code in a method if it is used multiple times.
- **Keep commit summaries short.** If it needs more details, place two new lines after the summary line and write away.
- **Test your code.** We're not interested in broken code, for the obvious reasons.
- **Write unit tests.** While this is strictly optional, we recommend it for complicated methods, where it is possible.
- **Use a topic branch.** So that we're immediately knowing what a branch is doing,
open a pull request from a topic branch (/feature/fix/docs/ branch (right side)),
following with name of the targeted branch and a short title instead of your main branch: [Examples](#PR-Branches)
- **Include license information.** We're not interested in missing license information
or copyright headers or similar things, because of that you should include the required information where necessary.
[How to do it?](#add-license-and-copyright-information)

## Use a Personal Fork and not Organization
BTDstudios will routinely modify your PR, whether it's a quick rebase or to take care
of any minor change we might want to have. Often, it's better for us to solve these
problems for you than make you go back and further trying to fix it yourself.

Unfortunately, if you use an organization for your PR, it prevents BTDstudios from
modifying it. This requires us to manually merge your PR, resulting in us
closing the PR instead of marking it as merged.

We much prefer to have PRs shown as merged, so please do not use repositories
on organizations for PRs.

See <https://github.com/isaacs/github/issues/1681> for more information on the
issue.

## Newcomers
If you are a newcomer contributor, look for the label `good first issue`.
Issues labeled like that can be resolved without having an
in depth knowledge about the codebase you are contributing to.

## Requirements
To get started with PRing changes, you'll need the following software:

- `Git`
- A Java17 or later JDK:
  - [Adoptium](https://adoptium.net/) has builds for most operating systems.

## Add License and Copyright information
### License / Copyright Header
- To check if all license headers are included in the right way run the Gradle task `checkLicenses`.
The task will fail if something is not correct.
- To include or update (after failed check task or header changes) run the Gradle task `updateLicenses`.

### Dependency Licenses
If you want to add a dependency look at its license and check if it is compatible.
After that put a notice into a folder with the name `LICENSES` located at the root path of that (sub-)project.
This file has to be named after the dependency name (`dependency_name.txt`) and has to follow the license guidelines 
and the informations in the source repository. Basically, in most licenses a note from a 
`NOTICE` (or similarly named) file must be inserted here. If such a file does not exist, 
insert a copy of the attached dependency license text. Don't forget to start each notice file
with the project name in the first, followed by a link to the repository in
the second line and start the contents of the notice after an blank line in between.
In gernal, always put a file named after the license title with the unmodified license text 
in the folder, if it is not already present or is not the (sub-)project's license.

## IDE Configuration
If a project has a code style policy, you can find an `.editorconfig` file in the root directory of the project.
If you're using IntelliJ, you can install the `EditorConfig` plugin.
Writing or reformatting files now follows our standards.

## Examples
### PR-Branches
This is **GOOD**:
````text
fix/main/missing-settings
feature/dev/add-updater
docs/main/document-updater-setting
````
This is **ACCEPTABLE**:
````text
fix/missing-settings
feature/add-updater
docs/document-updater-setting
````
This is **BAD**:
````text
missing-settings
abc/abc
modify-code
````

### Code-Style
This is **GOOD**:
````text
if (var.func(param1, param2)) {
    // do something
}
````
This is **BAD**:
````text
if( var.func( param1, param2 ))
{
           // do something
}
````
