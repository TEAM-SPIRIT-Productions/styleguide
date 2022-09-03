# Team SPIRIT Style Guide and Contribution Standards

As Team SPIRIT grows in not just numbers but also competency, there may be a divergence of styles. This document serves to lay foundations for our projects, and keep everyone on the same page, making things like setting linting rules much easier.

## Code Style and Conventions

As much as possible, we would prefer to keep to [Google Style Guides](https://github.com/google/styleguide) for language-specific style and convention.  
This will be our standard moving forward, unless otherwise noted in the repository.

## Git Commit Messages

Git commit messages should be written in present tense, and in [imperative grammatical mood](https://en.wikipedia.org/wiki/Imperative_mood).

They should be prefixed with a *type* to indicate what kind of commit they are.

| Type | Function |
| --- | --- |
| DOCS | Changes to documentation |
| FEAT | Adding a new file/feature |
| FIX | Fixing a bug |
| PERF | Improvements to performance |
| REFACTOR | Restructure the code without changing external behaviour |
| STYLE | Changes that do not affect semantics (e.g. adding whitespaces or fixing indents) |
| Revert | Revert a previous commit |
| CHORE | Any other business |

Commits that revert previous commits should take the form:

- Header:
    ```
    Revert "<header of the reverted commit>"
    ```
- Body:
    ```
    This reverts commit <hash of reverted commit>.
    ```

To clarify that a commit pertains to a particular feature, a *scope* can be added in parentheses after the *type*. This is optional.

Any potentially changes should be marked with a `!`, after the *type*/*scope*.

Example usages for clarity:
> git commit -S -m "CHORE: Reduce NX rate" src/main/java/net/spirit/ms/constants/GameConstants.java

> git commit -m "FIX: Increase global drop rate" -m "Drop rate accidentally lowered previously" src/main/java/net/spirit/ms/constants/GameConstants.java

> git commit -S -am "FEAT(RewardBox)!: Make account-wide boxes default" -m "BREAKING CHANGE: API for using reward boxes has changed."

If the above change (which generated a commit hash of `2b1e045`) was bad, the command to undo it is:
> git revert 2b1e045

*Git should automatically generate something like this in an editor:*
> Revert "FEAT(RewardBox)!: Make account-wide boxes default"
> 
> This reverts commit 2b1e045a8eee91df0bba16160d0967ce258d86f9.

You may simply save and exit, if you don't wish to add any more details.

## Versioning

For small projects with few updates, we prefer [Semantic Versioning](https://semver.org/). This is the de facto versioning scheme we will use for projects with public APIs. That is to say, the format is `MAJOR.MINOR.PATCH`:  
- `MAJOR`: incompatible API changes
- `MINOR`: backwards-compatible changes
- `PATCH`: backwards-compatible bug fixes

For larger projects with more rapid internal development (especially those without obvious public-facing APIs), we prefer Spirit Versioning. The format for Spirit Versioning 2 is `YYYY:FEATURE:PATCH`:
- `YYYY`: year of (pre-)release/tagging (e.g. `2022`)
- `FEATURE`: Number of feature updates since the last `year` increment
- `PATCH`: Number of non-feature updates since the last `year` increment
    - e.g. bug fixes, refactors, style changes, dependency updates

## Platforms and Software Versions

Unless otherwise noted, these are the target platforms and software tool versions we will use and support for our internal projects.

- OS:
    - Windows 10 Pro
    - Windows 11 Home
    - Windows 11 Pro
    - Ubuntu 22.04 LTS
- VCS:
    - Git 2.35.2+
    - GitHub
- Shell/Terminal:
    - PowerShell 7
    - Bash
    - Windows Terminal
    - GNOME Terminal
- Java:
    - OpenJDK 17 LTS
- Python:
    - Jython 2.7 (legacy)
    - CPython 3.8+ (minimum)
    - CPython 3.10 (target)
- Text Editor/IDE:
    - VS Code/vscodium
    - Nano
    - IntelliJ Community Edition
    - PyCharm Community Edition
- Database Management/Administration
    - WAMP 3.2.6
    - MySQL 5.7
    - MySQL Workbench 8.0 CE