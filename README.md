# buildkite-docker-example
Source code for [How to set up Continuous Integration for monorepo using Buildkite](https://adikari.medium.com/set-up-continuous-integration-for-monorepo-using-buildkite-61539bb0ed76)

Overview
The monorepo, serves as a unified, version-controlled repository that houses multiple independent projects, giving you flexibility, easy management, and a simpler way to keep track of changes and dependencies across different repositories.

With a monorepo, you can:
Cut down on the extra work of copying code for microservices.
Keep an eye on and manage the whole codebase without jumping between different places.


##How to use

###Requirements 
Webhooks
Folders/SubFolders
monorepo-diff Plugin



Create Webhooks, we will be using the 



Create Folders/ Sub folders in your repository to use, we have app and test folder in the root of our application. 

We would be using the buildkite monorepo-diff plugin 


Pipeline.yml
