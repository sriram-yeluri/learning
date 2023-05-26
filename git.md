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

## How to remove untracked files 

```sh
git clean -n  # perform dry run
git clean -nd # dry run to list down the folders
git clean -f # remove untracked files
git clean -fd # remove untracked files and folders
git clean -fx # remove untracked and ignored files
```

## Deleting remote branches

```sh
# check the remote branches 
git branch -a

# delete the remote branch
git push origin --delete <branch_name>
or
git push origin -d <branch_name>
```

## Deleting local branches

```sh
git branch -d <branch_name>
# use the -D flag for force delete (--delete --force)
git branch -D <branch_name>
```
