# Managing Git repositories

## CleanUp of Local Git Branches

```sh
git branch --merged | egrep -v "(^\*|master|dev)" | xargs git branch -d

# git branch –merged : list all the branches currently merged with your current checked out branch;
# egrep -v “(^*|master|dev)” : invert matching of grep in order to exclude any branches that may be called “master” or “dev”
# xargs git branch -d : delete every single branch listed.
```
