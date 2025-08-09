# Jenkins & Git Pipeline Assessment
**Name:** Yogeswaran Ganesan  
**Date:** 2025-08-09
**GitHub Repo:** [jenkins-pipeline-demo](https://github.com/Yogeswaran424/jenkins-pipeline-demo)  
**Jenkins Version:** 2.452.1  

## Overview
This project demonstrates creating a GitHub repository, connecting it to Jenkins, setting up a pipeline to run every 7 days, introducing an intentional failure, fixing it, and validating the build process.
---

## Step-by-Step Implementation

I created a new public GitHub repository named `jenkins-pipeline-demo`

Created Jenkins file

Configured job to pull code from GitHub using Pipeline script from SCM.
Set branch to main.

Triggered pipeline manually for first run.
Verified success in Console Output.

Modified Jenkinsfile to use a non-existing branch name nonexistentbranch.
Pushed changes to GitHub.
Pipeline failed as expected.

Corrected Jenkinsfile to use main branch again.
Committed and pushed changes.
Reran pipeline, verified successful build.

Placed screenshots for each step under
-> Screenshots Folder