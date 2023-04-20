Common GitHub configurations for the Payfree GitHub organization.

# Shared

Links: 

* [github docs](https://docs.github.com/en/actions/using-workflows/sharing-workflows-secrets-and-runners-with-your-organization):
  * [shared actions](https://docs.github.com/en/actions/using-workflows/reusing-workflows)
  * [starter workflows](https://docs.github.com/en/actions/using-workflows/creating-starter-workflows-for-your-organization)

## actions

* [.github/workflows/gradle-tasks.yml](.github/workflows/gradle-tasks.yml):
  * setting up java, validate gradle and calls some gradle tasks
  * usage-example:
    ```yml
    name: compile-check on pull-request to master or main
    on:
      pull_request:
        branches: [ master, main ]

    jobs:
      build:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v3
          - name: compile and test
            uses: payfree-io/.github/.github/workflows/gradle-tasks.yml@main
            env:
              ORG_GRADLE_PROJECT_build_env_variable_key: variable_value
            with:
              gradle-tasks: build
    ```

## workflows
### gradle
 * [workflow-templates/gradle/pull-request.yml](workflow-templates/gradle/pull-request.yml): test and compile on pull request to a branch (by default the default one)
