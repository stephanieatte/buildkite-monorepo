# buildkite-monorepo-example


[![Add to Buildkite](https://buildkite.com/button.svg)](https://buildkite.com/new)


The monorepo, serves as a unified, version-controlled repository that houses multiple independent projects, giving you flexibility, easy management, and a simpler way to keep track of changes and dependencies across different repositories.

* Reduce overhead associated with duplicating code for microservices.
* Easily maintain and monitor the code
  
## How to use

Create Folders and/or Sub folders in therepository to use, we have app and test folder in the root of our application for example

#### Webhooks

Configure Webhooks in the Github Repository settings for your pipeline to subscribe to Pushes, Deployemnts and Pull Requests events that occur in a specific repositor. You must be a repository owner or have admin access in the repository to create webhooks in that repository.

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

See [**How to set up Continuous Integration for monorepo using Buildkite**](https://adikari.medium.com/set-up-continuous-integration-for-monorepo-using-buildkite-61539bb0ed76) for step-by-step instructions on how to get this running, or click the Add to Buildkite to start




This repository is an example [Buildkite](https://buildkite.com/) pipeline for running a simple bash script, [script.sh](script.sh).

The script simply prints some debug output with an inline image, some artifacts, and exits with a success code (0).

See the full [Getting Started Guide](https://buildkite.com/docs/guides/getting-started) for step-by-step instructions on how to get this running, or simply click the following link to add this project to Buildkite:

## License

See [License.md](License.md) (MIT)

