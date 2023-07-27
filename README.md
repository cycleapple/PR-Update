Sure! Here's the README for your custom GitHub Action "Merge Base Branch into PR":

# Merge Base Branch into PR

## Description

The "Merge Base Branch into PR" GitHub Action automates the process of checking if the pull request branch is up to date with its base
branch and performs the merge if necessary. It helps ensure that the pull request always includes the latest changes from the base
branch before further processing.

## Features

- Automatically checks if the pull request branch is up to date with its base branch.
- Performs a merge of the base branch into the pull request branch if the branches are not up to date.
- Flexible and customizable, allowing you to specify the base branch dynamically in your workflow.

## Usage

To use the "Merge Base Branch into PR" action in your GitHub workflows, follow these steps:

### Inputs

The action requires the following input:

- `baseBranch` (required): The base branch to compare and merge with the pull request branch.

### Example Workflow

Here's an example of how to use the "Merge Base Branch into PR" action in your GitHub workflow:

```yaml
name: Merge Base Branch into PR

on:
  pull_request:
    types:
      - opened
      - synchronize

jobs:
  merge_base_branch:
    runs-on: ubuntu-latest
    steps:
      - name: Merge Base Branch into PR
        uses: cycleapple/PR-Update@v1
        with:
          baseBranch: ${{ github.event.pull_request.base.ref }}
```

## License

This project is licensed under the [MIT License](LICENSE).

