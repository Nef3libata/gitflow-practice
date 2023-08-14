# Gitflow Practice Documentation

## Table of Contents

- [Gitflow Practice Documentation](#gitflow-practice-documentation)
  - [Table of Contents](#table-of-contents)
- [Workflow](#workflow)
  - [General Explanation \& Diagram](#general-explanation--diagram)
    - [Workflow for Adding a Feature:](#workflow-for-adding-a-feature)
    - [Workflow for `hotfix`:](#workflow-for-hotfix)
    - [Diagram:](#diagram)
  - [Branches](#branches)
    - [`master`:](#master)
    - [`develop`:](#develop)
    - [`feature`:](#feature)
    - [`test`:](#test)
    - [`hotfix`:](#hotfix)


# Workflow

## General Explanation & Diagram
### Workflow for Adding a Feature:
For adding a new feature, a `feature` branch is first created from the `develop` branch. Once the feature is completed, it is merged back to `develop` branch. When the `develop` branch is ready to be merged with ``master`` branch, it is pushed to test branch so it is checked that everything works as intended. If the test is successful, the code is merged to `master` and `develop` branch.

### Workflow for `hotfix`:
When a bug happens in production code, a `hotfix` branch is created from the `master` branch. The bug is fixed in the hotfix branch and when it is fixed, it gets merged back to `master` branch. The `develop` branch is merged with `master` branch.

### Diagram:
The picture below visualizes this workflow:

![Modified Gitflow diagram](/img/diagram.jpg)
## Branches
### `master`:
In this workflow, the main branch is `master` branch. This branch represents the main codebase and contains the stable and production-ready code. It should always be in a deployable state. Typically, releases are made from this branch. The `master` branch should only be updated through merging other branches into it, such as the `hotfix` branch or the test branch.
### `develop`:
This branch is used for ongoing development. It serves as an integration branch for all the features and bug fixes developed in `feature` branches. When a feature or bug fix is complete in the `feature` branch, it is merged into the `develop` branch. The `develop` branch should always contain the latest stable code that is ready for further testing or deployment.

### `feature`:
These branches are created for developing new features or fixing specific bugs. Each feature or bug fix should have its own dedicated branch. `feature` branches are created from the `develop` branch and are used to make the necessary changes. Once a feature is complete, it can be merged back into the `develop` branch.

### `test`:
This branch is used for integration testing. When new features or bug fixes are developed in `feature` branches and merged with develop, they can be tested together in the test branch to ensure they work well together and do not introduce any conflicts or issues. Once the testing is complete and all the features are stable, the changes can be merged into the `develop` branch and `master` branch.

### `hotfix`:
This branch is used to fix critical bugs or issues in the production code. When a bug is discovered in the `master` branch, a new `hotfix` branch is created from it. The `hotfix` branch is then used to make the necessary changes and test them. Once the hotfix is complete, it is merged back into the `master` branch, and the changes are deployed to production.
