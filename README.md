# git-aliases

This is my collection of git alias command (many of which have been pilfered from across the web)

## Aliases

### SAVE

Stage and commit with a message all changes.

```config
save = !git add -A && git commit -m
```

### SYNC

```config
sync = !git pull --rebase --prune $@ && git submodule update --init --recursive
```

### LOL

Show the history in a pretty format

```config
lol = log --oneline --graph --decorate --all
```

## COB

Saves some keystrokes when creating a new branch

```config
cob = checkout -b
```

### UNDO

Undo the last commit you made.

```config
undo = reset HEAD~1 --mixed
```

### BCLEAN

Pull down the most recent version of `master` and requests to delete any local branches that match the updated `master` branch

```config
bclean = "!foo() { git checkout master && git sync && git branch --merged master | grep -v " master$" | xargs -p -r git branch -d; }; foo"
```
