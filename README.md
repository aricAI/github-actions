# AIND GitHub Actions (Reusable Workflows)
aind-github-actions

[![License](https://img.shields.io/badge/license-MIT-brightgreen)](LICENSE)
[![semantic-release: angular](https://img.shields.io/badge/semantic--release-angular-e10079?logo=semantic-release)](https://github.com/semantic-release/semantic-release)
![GitHub tag (latest SemVer pre-release)](https://img.shields.io/github/v/tag/AllenNeuralDynamics/aind-github-actions?include_prereleases&sort=semver)

## This repository is for workflows that may be reused in other worflows and repositories.

GitHub actions workflows are found in .github/workflows




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
