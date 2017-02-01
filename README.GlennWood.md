
# Glenn Wood's Pre-Interview DevOps Task

## Overview

Glenn addresses this [challenge]README.md using DevOps design patterns he is familiar with, which 
include:

* A CI/CD pipeline fully provisioned in its own VM.
   - which provides the Jenkins service
   - and docker and docker-compose for provisioning common services (such 
   as mySql, postgresql, etc.)
   - Build and test in same environment (separation may be addressed later)
* Jenkins will build, deploy and test each component in their own jobs
   - Initially, dependencies will be hand-configured in Jenkins job configs
   - Jenkins will poll github for changes
* Each component will be built using its particular build convention
   - with a language-specific Jenkins plugin, if available and practical
* Advanced provisioning will be provided on a time-available basis
   - Dependency diagram
   - Test reports/diagrams integration in Jenkins
   - An automated dependency configuration
   - Separation of build and test environments
   
## The Plan

* Provision a VM (CentOS7)
   - Docker
   - docker-compose
   - Jenkins
* Provision a "Hello, World" Jenkins job for each component
   - including github polling
   - and hand-configured job dependencies
* Configure actual build of each component
   - using its language specific build process
   - using a Jenkins plugin, if available and practical
* Compose primitive unit-tests for each component
   - initially just a smoke-test
   - then executing the script illustrated in each typescript file
   - explore integrations with Jenkins in each language
   - This will include suggesting and implementing "individual developer build and/or coding practices in some cases".
* Compose integration test
   - exercising the sequence illustrated in the LamportDiagram
   - touch some files in github and watch her go
* Bonus
   - Implement a continuous integration solution - DONE
   - Deploy to a cloud provider - I would use Google Platform if we get this far
   - Deploy to an emulated physical infrastructure in DeterLab - I would need an account in 
     DeterLab (if we get this far).