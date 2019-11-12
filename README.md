# Automilestone

![Autobadger Release Stability](https://img.shields.io/static/v1?label=stability&message=unusable&style=flat-square&color=red)
![Autobadger Latest Release](https://img.shields.io/static/v1?label=latest&message=0.0.0&style=flat-square&color=purple)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/bc49f95e55bc499a90ac399534b3bc75)](https://www.codacy.com/gh/autosuite/automilestone?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=autosuite/automilestone&amp;utm_campaign=Badge_Grade)

[_What are these badges?_](https://github.com/teaminkling/autobadger/tree/master/BADGES.md)

## Introduction

Whenever a commit is tagged with a prefix and then a SemVer milestone, a new milestone is created with the SemVer version found.

For example: `[pre-1.0.1] blah` will create the `1.0.1` milestone if the prefix is `pre-` (default).

## Usage

Add this action to your workflow using:

> Note that the `prefix` configuration is optional and defaults to `pre-`.

```yaml
name: my-workflow

on: [push]

jobs:
  autocommit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - uses: teaminkling/skip-commit@master
        with:
          commit-filter: skip-ci
      - uses: teaminkling/automilestone@master
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          github-repository: ${{ github.repository }}
          prefix: pre-
```

## Documentation

If you would like to contribute to this project, please read our [contributors documentation](CONTRIBUTING.md) and our [code of conduct](CODE_OF_CONDUCT.md).

The license we use for this project is defined in [the license file](LICENSE).

Thanks!
