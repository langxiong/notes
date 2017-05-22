# Q: `git clone --depth=1` 后， 无法在本地切换到远程分支
# A: `http://stackoverflow.com/questions/22984262/cannot-update-paths-and-switch-to-branch-at-the-same-time`

```shell
$ git branch -a
* master
remotes/origin/HEAD -> origin/master
remotes/origin/master
```

> The fix:

```shell
$ git remote set-branches --add origin branch-1
$ git remote set-branches --add origin branch-2
$ git fetch
```

> After:

````
$ git branch -a
* master
remotes/origin/HEAD -> origin/master
remotes/origin/branch-1
remotes/origin/branch-2
remotes/origin/master
```