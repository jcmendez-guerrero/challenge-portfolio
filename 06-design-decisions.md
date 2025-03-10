# 6 Design Decisions

<!-- TOC -->

- [Design Decisions](#design-decisions)
    - [Use of branch rather than tag](#use-of-branch-rather-than-tag)
    - [Conventional Commits](#conventional-commits)
    - [Reverts](#reverts)

<!-- /TOC -->

This Section aim to document all the architectural decisions taken

## 6.1 Use of branch rather than tag

| Problem | Constraints | Decision |
| --- | --- | --- |
| At the moment of selecting the best way to keep a “latest" or stable reference it was given the option to use a tag, in order to create a point on time decision to consider as a functional part of the JSL, other option was the use of a branch that will be updated from time to time | :children_crossing: The selected option need to be able to be reseted or force updated without impacting development or solution running. <br> :children_crossing: Tag and branch concept are refered to git as scm tool used on GitHub | The decision taken is to use a branch as per it point to commit objects instead than a single revision, this will allow an easier manipulation of fixes as well as release update as well as the force push, additionally, according to the git glossary the tag is not changed by a commit and therefore may not be suitable for the solution |

## 6.2 Conventional Commits

| Problem | Constraints | Alternatives | Decision |
| --- | --- | --- | --- |
| We need to use an automated release management that is capable to detect what kind of changes were made in order to generate a proper change log and be able to manipulate the releases if required | :children_crossing: The identification of the change as well as the release generation must be automatic | :twisted_rightwards_arrows: Accept any commit but rely on developer to tag the pull requests as they consider <br> :twisted_rightwards_arrows: Use conventional commits types to identify the type | To use conventional commits due that it allow the automatic identification of the change without additional intervention of a developer rather than the identification of the commit. |

## 6.3 Reverts

| Problem | Constraints | Alternatives | Decision |
| --- | --- | --- | --- |
| When a revert is required by any reason, the system may identify issues at sonar level due the not tested coverage or similar issues, this might go againts the controls of the standard pipeline if those are forced skipped. | :children_crossing: Sonar consider a revert as a new code <br> :children_crossing: Revert is done automatically from GitHub | :twisted_rightwards_arrows: Manual issues resolution <br> :twisted_rightwards_arrows: Skip controls for reverts | Reverts automatically created from Github can skip the controls due that if they are required is due an issue detected that is impacting the end users. The code is considered to be already in the code in the past and therefore was already tested. |
