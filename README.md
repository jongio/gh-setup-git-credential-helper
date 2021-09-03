# GitHub CLI Extension - Setup Git Credential Helper

When you fork a repo the default GITHUB_TOKEN has limited permissions that doesn't allow you to do common things like add secrets and doesn't allow you to use the GitHub CLI as a gitcredential helper.

This extension solves all of that for you.

It will:

1. Clear the `GITHUB_TOKEN` variable, so `gh auth login` won't complain that it already has a value.
2. Call `gh auth login`
3. Set `gh auth git-credentials` as your gitcredentials helper.


The full context for this extension can be found here: https://blog.jongallant.com/2021/06/codespaces-gh-cli-git-credentials/

Here are the related GitHub issues:

- https://github.com/cli/cli/issues/3796
- https://github.com/cli/cli/issues/3797
- https://github.com/cli/cli/issues/3798



## Installation

1. Install [GitHub CLI v2.0+](https://github.com/cli/cli)
1. Run `gh extension install jongio/gh-setup-git-credential-helper`

## Run
1. Run `gh setup-git-credential-helper` from within your Codespace or DevContainer
1. You will see "Successfully added 'gh auth git-credential' as your git credential helper." if it succeeded.  Please file an issue if you have any problems.

## Uninstall
1. Run `gh extension remove gh-setup-git-credential-helper`

## Install in DevContainer

See the code in this repo in /.devcontainer to see how to add this to your devcontainer

1. Copy the `github-debian.sh` script to library-scripts
1. Add the install command to your Dockerfile
    ```bash
    RUN apt-get update && export DEBIAN_FRONTEND=noninteractive && bash /tmp/library-scripts/github-debian.sh
    ```
1. Manually run `gh setup-git-credential-helper` when your container starts.


## Error Messages

Including the following error messages for SEO - this extension should fix all of these issues.

```
failed to fetch public key: 
HTTP 403: Resource not accessible by integration
```

```
The value of the GITHUB_TOKEN environment variable is being used for authentication.
To have GitHub CLI store credentials instead, first clear the value from the environment.
```

```
git push --set-upstream origin env-dev5
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/jongio/golang-sample-app/'
```