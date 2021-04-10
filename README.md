# Git Repo Sync

![build](https://github.com/wangchucheng/git-repo-sync/workflows/build/badge.svg)
![license](https://img.shields.io/github/license/wangchucheng/git-repo-sync)

Git Repo Sync enables you to synchronize code to other code management platforms, such as GitLab, Gitee, etc.

## Try Git Repo Sync

You can use the following example as a template to create a new file with any name under `.github/workflows/`.

```yaml
name: <action-name>

on: 
  - push
  - delete

jobs:
  sync:
    runs-on: ubuntu-latest
    name: Git Repo Sync
    steps:
    - uses: actions/checkout@v2
      with:
        fetch-depth: 0
    - uses: wangchucheng/git-repo-sync@v0.1.0
      with:
        # Such as https://github.com/wangchucheng/git-repo-sync.git
        target-url: <target-url>
        # Such as wangchucheng
        target-username: <target-username>
        # You can store token in your project's 'Setting > Secrets' and reference the name here. Such as ${{ secrets.ACCESS_TOKEN }}
        target-token: <target-token>
```