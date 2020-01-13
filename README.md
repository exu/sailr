# Sailr (zsh compatible version) 

Based on [@craicoverflow github version]()

Sailr helps you follow the [Conventional Commits](https://www.conventionalcommits.org) conventional by installing a configurable `commit-msg` into your Git projects.

## Table of Contents
+ [About](#about)
+ [Getting Started](#getting_started)
+ [Usage](#usage)

### Prerequisites

To use Sailr, you must have [jq](https://stedolan.github.io/jq/download/) installed.

### Installing

```sh
curl -o- https://raw.githubusercontent.com/exu/sailr/master/scripts/install.sh | bash
```

### Uninstalling

Remove the `commit-msg` Git hook from your project:

```sh
rm <your-project>/.git/hooks/commit-msg
```

## Usage <a name = "usage"></a>

Once installed, you must run `git init` in your Git projects to (re)initialize your repository. The hook will look for a configuration file in the following locations (in order):

1. The root of your Git project.
2. `SAILR_CONFIG`: You can set a custom location for your `sailr.json` config by setting the `SAILR_CONFIG` environment variable. Example: `SAILR_CONFIG=$HOME/.sailr/sailr.json`.

```json
{
    "enabled": true,
    "revert": true,
    "length": {
        "min": 1,
        "max": 52
    },
    "types": [
        "build",
        "ci",
        "docs",
        "feat",
        "fix",
        "perf",
        "refactor",
        "style",
        "test",
        "chore"
    ]
}
```

**Note**: you can disable Sailr in your project by setting `enabled` to `false` in `sailr.json`.

### Unit Testing

Unit tests are written in Python. They are located in `./tests`

To run all tests:

```sh
make test
```