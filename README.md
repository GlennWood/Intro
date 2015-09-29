
# Pre-Interview DevOps Task

## Dependency Management

Good dependency management is fundamental to agile development. As a research institute with a large capacity for research, but limited capacity for nuts and bolts development, leveraging OSS projects in both our code and infrastructure is a must. To do this, however, introduces the complexity of dependency management. Moreover, we are a group of coordinated but in many ways independently working researchers developing a testbed infrastructure that is itself experimental. In the ideal case the functionality of the testbed is provided through a collection of horizontally integrated components. In addition to external dependency management, this introduces protocol-version dependencies between components as well as client library direct software dependencies. As a DevOps engineer at ISI you will be helping world class researchers, who are not necessarily world class developers, leverage the state of the art in dependency management tools and techniques to the benefit of the individual researchers time and the overall coherency of the testbed infrastructure we provide. Keeping in mind that the goal is to provide development solutions to researchers that 'just work' and are synergistic with respect to their own workflow, in whatever programming language they may be using.

## Build Management

Build management is closely tied to dependency management. The task is conceptually very simple. Given a (distributed) code base together with it's dependencies and a target environment, produce a set of binaries and configurations that can provide the testbed functionality in the target environment. Because a network testbed is a set of distributed components which, themselves facilitate the execution of code within a networked environment, the tools that build the testbed components must have an intricate understanding of the deployment environment to produce a functioning set of binaries and configurations. To the extent possible we would like to minimize the amount of information the build tools require in favor of auto-configuring components. However, build-time information such as target operating system and processor architecture are unlikely to be elided in favor of runtime auto-configuration anywhere in the near future. As a DevOps engineer you will be responsible for integrating researcher code into the overall testbed build environment. You will also be responsible for developing, maintaining and evolving that build environment as the demands on the testbed itself evolve and new components are developed.


## API & Integration Testing

Dependency and build management are futile activities without API testing in place, especially in a horizontally integrated infrastructure. In a network testbed it is important to consider API in the broad sense of the word e.g., what functionalities does the testbed provide to the users. This can come in the form of an actual API like a REST interface, or it could come in a more subtle form like how environment variables are set up on testbed nodes or how network interfaces are named, addressed and assigned. Automated testing of a network testbed API in this broad sense is a significant challenge. Integration testing in our context is ensuring that the binaries and configurations produced by the build produce a properly functioning testbed within the target environment. Indeed, a great deal of integration testing may be implicit in API testing. However, because the various components that make up the testbed environment are unlikely to progress uniformly, having tests that isolate internal integration and component interaction issues versus simply observing testbed malfunction at the user level can greatly reduce diagnosis time. As a DevOps engineer you will be responsible for writing and maintaining many of these tests, and when bugs do arise you will work with developers to develop diagnostic tests that isolate the root cause in addition to patching and building a working solution.

## The Task

You were directed a GitHub repository that contains this README. That repository is a part of a mock GitHub organization that contains several code repositories. These repositories represent a set of components that are *capable* of working together to solve the common task of making digital pizzas. Each of these repositories contains code written a different programming language, and has a variety of dependencies which are in no way managed. In other words, these repositories are representative of typical research-grade code. Attached to this repository you will also find a functional specification of sorts describing how the system should work from the users perspective as well as how all the internal components should interact with one another. You are also given three deployment environments which are DETERLab network environment descriptions together corresponding JSON descriptions (so you don't have to write a TCL parser, _dont_ write a TCL parser). Your build tool should 

  + Automatically pull the dependencies of each component from upstream sources and provide a built in path for upgrade migration
  + Produce a functioning digital pizza production system in each of the given environments
  + Verify the system does indeed work in each environment through at least partially automated tests
