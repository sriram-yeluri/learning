# Managing Git repositories

## CleanUp of Local Git Branches

```sh
git branch --merged | egrep -v "(^\*|master|dev)" | xargs git branch -d

# git branch –merged : list all the branches currently merged with your current checked out branch;
# egrep -v “(^*|master|dev)” : invert matching of grep in order to exclude any branches that may be called “master” or “dev”
# xargs git branch -d : delete every single branch listed.
```

## CleanUp Remote Tracking Branches
In order to clean up remote tracking branches, meaning deleting references to non-existing remote branches, use the `git remote prune` command and specify the remote name.

```sh
$ git remote prune <remote>

# In order to find the name of your current configured remotes, run the “git remote” command with the “-v” option.
$ git remote -v

# So , if the remote name is “origin”, then
$ git remote prune origin
```
