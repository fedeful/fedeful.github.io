---
layout: post
title: Git Workflow Tips
subtitle: Commands and habits that keep branches clean
tags: [git, dev, tools]
comments: true
---

Git commands I use daily and can never remember exactly.

## Undo last commit (keep changes staged)

```bash
git reset --soft HEAD~1
```

## Stash including untracked files

```bash
git stash -u
git stash pop
```

## Rebase onto main cleanly

```bash
git fetch origin
git rebase origin/main
```

## See what changed in a commit

```bash
git show <commit-hash> --stat
git show <commit-hash> -- path/to/file.py
```

## Delete merged branches locally

```bash
git branch --merged main | grep -v "^\*\|main\|master" | xargs git branch -d
```

## Amend last commit message

```bash
git commit --amend -m "Better message"
```

## Useful aliases to add to `.gitconfig`

```ini
[alias]
  st = status -sb
  lg = log --oneline --graph --decorate --all
  undo = reset --soft HEAD~1
```

{: .box-note}
**Note:** Never force-push to shared branches without warning the team first.
