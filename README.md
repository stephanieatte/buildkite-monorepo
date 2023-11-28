# buildkite-monorepo-example

The monorepo, serves as a unified, version-controlled repository that houses multiple independent projects, giving you flexibility, easy management, and a simpler way to keep track of changes and dependencies across different repositories.

This approach allows teams to:
* Reduce overhead associated with duplicating code for microservices.
* Easily maintain and monitor the entire codebase.
  
## How to use

Create Folders/ Sub folders in your repository to use, we have app and test folder in the root of our application for example

#### Webhooks

Configure Webhooks in the Github Repository settings for your pipeline

#### monorepo-diff-buildkite-plugin
We would be using the buildkite monorepo-diff plugin, it will assist in triggering pipelines by watching folders in the `monorepo`.

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

Check out this post to learn [**How to set up Continuous Integration for monorepo using Buildkite**](https://adikari.medium.com/set-up-continuous-integration-for-monorepo-using-buildkite-61539bb0ed76).


Pipeline.yml
