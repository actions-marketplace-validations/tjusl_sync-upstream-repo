# Sync Upstream Repo
This repository contains an github action to sync your current repository with an upstream repository. The work is greatly inspired by [actions-registry/github-repo-sync-upstream](https://github.com/actions-registry/github-repo-sync-upstream) which didn't work for me.

# Usage
Example github action:
```
 
name: CI

on: 
  schedule:
    - cron: "15 14 * * *"
jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v1
    - name: Fetch upstream
      uses: tjusl/sync-upstream-repo@v0.1.6
      with:
      #Git upstream repo
        upstream_repo: https://github.com/holger24/AFD.git
        upstream_branch: master
        local_branch: master
	github_token: ${{ secrets.GITHUB_TOKEN }}

```

This action syncs your repo with the upstream repo ``` https://github.com/holger24/AFD.git ``` every day at 14:15 UTC.

