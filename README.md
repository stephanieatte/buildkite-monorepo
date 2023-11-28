# buildkite-docker-example

The monorepo, serves as a unified, version-controlled repository that houses multiple independent projects, giving you flexibility, easy management, and a simpler way to keep track of changes and dependencies across different repositories.

With a monorepo, you can:
Cut down on the extra work of copying code for microservices.
Keep an eye on and manage the whole codebase without jumping between different places.


## How to use
Webhooks
Folders/SubFolders
monorepo-diff Plugin

### monorepo-diff-buildkite-plugin

This plugin will assist you in triggering pipelines by watching folders in your `monorepo`.

Check out this post to learn [**How to set up Continuous Integration for monorepo using Buildkite**](https://adikari.medium.com/set-up-continuous-integration-for-monorepo-using-buildkite-61539bb0ed76).


```yaml
steps:
  - label: "Triggering pipelines"
    plugins:
      - buildkite-plugins/monorepo-diff#v1.0.1:
          diff: "git diff --name-only HEAD~1"
          watch:
            - path: "app/"
              config:
                trigger: "app-deploy"
            - path: "test/bin"
              config:
                command: "echo Make Changes to Bin"
```



Create Webhooks, we will be using the 



Create Folders/ Sub folders in your repository to use, we have app and test folder in the root of our application. 

We would be using the buildkite monorepo-diff plugin 


Pipeline.yml
