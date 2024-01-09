# GitHub Actions (Reusable Workflows)
github-actions

[![License](https://img.shields.io/badge/license-MIT-brightgreen)](LICENSE)

## This repository is for workflows that may be reused in other workflows and repositories.

GitHub actions workflows are found in .github/workflows.

### Call the "lint" workflow with:
```
jobs:
  lint:
    uses: aricAI/github-actions/.github/workflows/lint.yml@main
    with:
      path_include: 'src' # optional, default: '**'
      path_exclude: 'src/.github' # optional, default: ''
    secrets:
      SERVICE_TOKEN: ${{ secrets.SERVICE_TOKEN }} # required
    env: # optional
      # these will override the defaults in the workflow
      # see https://github.com/github/super-linter#environment-variables
      # non-default config files
      PYTHON_BLACK_CONFIG_FILE: pyproject.toml
      PYTHON_ISORT_CONFIG_FILE: pyproject.toml
      ... # other non-default config files
      # disable linters
      VALIDATE_PYTHON_PYLINT: false
      ... # other linters to disable
```
### Call the "tag" workflow like this:
```
jobs:
  bump-version:
    uses: aricAI/github-actions/.github/workflows/tag.yml
    with:
      default_branch: main # optional, default: main
    secrets:
      SERVICE_TOKEN: ${{ secrets.SERVICE_TOKEN }} # required
```

### Pull requests

For internal members, please create a branch. For external members, please fork the repository and open a pull request from the fork. We'll primarily use [Angular](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#commit) style for commit messages. Roughly, they should follow the pattern:
```text
<type>(<scope>): <short summary>
```

where scope (optional) describes the packages affected by the code changes and type (mandatory) is one of:

- **build**: Changes that affect build tools or external dependencies (example scopes: pyproject.toml, setup.py)
- **ci**: Changes to our CI configuration files and scripts (examples: .github/workflows/ci.yml)
- **docs**: Documentation only changes
- **feat**: A new feature
- **fix**: A bugfix
- **perf**: A code change that improves performance
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **test**: Adding missing tests or correcting existing tests
