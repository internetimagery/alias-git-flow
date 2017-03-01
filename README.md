# Alias = "Git Flow!"

This method adds some commands to follow the excellent [git flow methodology](http://nvie.com/posts/a-successful-git-branching-model/) using simple git aliases.

To use them, simply copy the text below into your git config file:

```
[alias]
  feature = "!git checkout develop && echo feature | git"
  release = "!git checkout develop && echo release | git"
  hotfix = "!git checkout master && echo hotfix | git"
  support = "!git checkout master && echo support | git"

  start = "!read BRANCH && git checkout -b $BRANCH-$1 && echo Starting"
  finish = "!read BRANCH && git merge $BRANCH-$1 --no-ff && echo Merging"

  publish = "!git push origin `git symbolic-ref --short HEAD`"
```

You can find the config file:

* Locally in a repo: ".git/config"
* Globally: "~/.gitconfig"


To use git flow. Ensure you first have a branch named "develop". `git branch develop`

Then start a new feature: `git feature start my-feature`

Work on your feature. Committing etc all you like. Then finally finish the feature and merge it back: `git feature finish my-feature`

The same start / finish functionality applies to the other tasks of git-flow.

```
git release start <name>
git release finish <name>
git hotfix start <name>
git hotfix finish <name>
git support start <name>
git support finish <name>
```

Hopefully this improves your git workflow! :heart:

Please, those more experienced with git/bash than I, send pull requests / issues / comments!
