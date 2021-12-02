# Quilt prepare GitHub Action

This repo contains a [GitHub Action](https://github.com/features/actions) that you can use to install all your workspace’s dependencies. This action is a wrapper over the [checkout](https://github.com/actions/checkout) and [setup-node](https://github.com/actions/setup-node) actions; it will checkout your repo and install dependencies using Yarn 2 (with optimal caching).

To use this action, create a [new workflow](https://docs.github.com/en/actions/quickstart#creating-your-first-workflow), and include this repo’s action as the first step in one of your jobs:

```yml
name: CI
on: [push]
jobs:
  lint:
    name: Lint 💅
    runs-on: ubuntu-latest
    steps:
      - uses: quilt-framework/action-prepare@v1
      - uses: quilt-framework/action-lint@v2
```
