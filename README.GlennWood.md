
# Glenn Wood's Pre-Interview DevOps Task

## Overview

Glenn addresses this [challenge](README.md) using DevOps design patterns he is familiar with, which 
include:

1. A CI/CD pipeline fully provisioned in its own VM
   - which provides the Jenkins service
   - and docker and docker-compose for provisioning common services (such 
   as mySql, postgresql, etc.)
   - Build and test in same environment (separation may be addressed later)
2. Jenkins will build, deploy and test each component in their own jobs
   - Initially, dependencies will be hand-configured in Jenkins job configs
   - Jenkins will poll github for changes
3. Each component will be built using its particular build process
   - with a language-specific Jenkins plugin, if available and practical
4. Advanced provisioning will be provided on a time-available basis
   - Dependency diagram
   - Integration of test reports/diagrams in Jenkins
   - An automated dependency configuration
   - Separation of build and test environments
   
## The Plan

0. Document the building of the build environment itself as we go along
1. [x] Provision a VM (CentOS7)
   - Docker
   - docker-compose
   - Jenkins
2. [ ] Provision a "Hello, World" Jenkins job for each component
   - including github polling
   - and hand-configured job dependencies
3. [ ] Configure actual build of each component
   - using its language specific build process
   - using a Jenkins plugin, if available and practical
4. [ ] Compose primitive unit-tests for each component
   - initially just a smoke-test
   - then executing the script illustrated in each typescript file
   - explore integrations with Jenkins in each language
   - This will include suggesting and implementing "individual developer build and/or coding practices in some cases".
5. [ ] Compose integration test
   - exercising the sequence illustrated in the LamportDiagram
   - touch some files in github and watch her go
6. [ ] Bonus
   - Implement a continuous integration solution - DONE
   - Deploy to a cloud provider - I would use Google Platform if we get this far
   - Deploy to an emulated physical infrastructure in DeterLab - I would need an account in 
     DeterLab (if we get this far).
   - "target operating system and processor architecture" variance
     - each component may require its own OS environment (especially vis-a-vis DeterLab)
     - this calls for a separate VM for each such component
     - and the attendant cross-VM configurations (endpoints, common environment variables, etc.)
   - Script the building of the build environment itself