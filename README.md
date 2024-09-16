# Crosslink Deployment Manual For Beginners

## Introduction

This document covers the deployment procedure for Crosslink Sub-Modules.

## Procedure

- Go to parent repository of OSS-Check, i.e., https://github.com/TTS-AMDOCS/OSS-check
- Create a FORK, and make sure all branches are forked, for example https://github.com/rohan-amdocs/OSS-check
- Clone this Fork locally, i.e., wherever you will be working.
- To set upstream run -> `git remote add upstream <sub-module url>` 
- Go to the Sub-Module you are working on, for example https://github.com/TTS-AMDOCS/crosslink-oss-controller
- Create a Fork and make sure all branches are forked, for example https://github.com/rohan-amdocs/crosslink-oss-controller
- Clone this Fork locally, i.e., wherever you will be working.
- To set upstream run -> `git remote add upstream <sub-module url>` 
- Go to your Local Clone of Sub-Module Fork, then checkout dev and run -> `git fetch upstream/dev` -> `git merge upstream/dev`
- Now that your Local Clone dev has latest changes, create a New Branch from dev. 
- Make your changes to this New Branch, once done, push to Origin HEAD and publish this New Branch.
- So now Sub-Module Fork New Branch has your changes.
- Create a PR from Sub-Module Fork New Branch to Sub Module dev, so your changes will come to Sub Module dev.
- Create a PR from Sub-Module dev to Sub-Module main, so your changes will come to Sub Module main.
- Create a Release based on the work done in the PR, using git convention.
- Go to your Local Clone of OSS-Check-Fork, then checkout dev and run -> `git fetch upstream` -> `git merge upstream/dev`
- Now that your Local Clone dev has latest changes, create a New Branch from dev.
- Follow this naming convention: *Bump-ms-oss-controller-to-v1.25.0*
- To ensure that the changes in Sub-Module reflect in this Bump Branch run -> `git submodule update --init <sub-module name>` ( If sub module is not initialized ) -> `git submodule update --remote <sub-module name>`
- Run -> `git add <sub-module name>` -> Commit to this Bump Branch
- Once done, push to Origin HEAD and publish this Bump Branch.
- So now OSS-Check Fork Bump Branch has your changes.
- Create a PR from OSS-Check Fork Bump Branch to OSS-Check dev, so your changes will come to OSS-Check dev.
- Go to your Local Clone of OSS-Check-Fork, then checkout test and run -> `git fetch upstream/dev` -> `git merge upstream/test`
- Now that your Local Clone test has latest changes, create a New Branch from test.
- Follow this naming convention: *Update-ms-oss-controller-to-v1.25.0*
- To pick commits in this Update Branch run -> `git cherry-pick <commit hash>`
- Once done, push to Origin HEAD and publish this Update Branch.
- So now OSS-Check Fork Update Branch has your changes.
- Create a PR from OSS-Check Fork Update Branch to OSS-Check test, so your changes will come to OSS-Check test.
- SSH to .5 server and follow deployment steps.
