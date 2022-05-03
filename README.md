Common GitHub configurations for the Payfree GitHub organization.

# shared actions

* .github/workflows/gradle-tasks:
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
