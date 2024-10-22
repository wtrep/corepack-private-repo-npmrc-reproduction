# 32098

Reproduction for Renovate issue [REPLACE_ME]().

## Current behavior

Updates to the `packageManager` digest fails on projects with private dependencies.

We can see that renovate will run `corepack use pnpm@9.12.2` to update the pnpm digest. The command fails because it is executed before the `.npmrc` file is generated.

This is not an issue with the `.npmrc` file as updates to private dependencies are working as expected (see [Update dependency @private/dependency to v1.0.1](https://github.com/wtrep/corepack-private-repo-npmrc-reproduction/pull/2)).

## Expected behavior

1. `corepack use pnpm@9.12.2` should be executed after the `.npmrc` file is configured/generated.
1. The pnpm version/digest should be updated successfully.

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/32098
