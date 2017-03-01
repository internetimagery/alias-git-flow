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

### You can find the config file:

* Locally in a repo: ".git/config"
* Globally: "~/.gitconfig"

As a local alias shortcut: `curl https://raw.githubusercontent.com/internetimagery/alias-git-flow/master/config >> .git/config`


### Usage

To use git flow. Ensure you first have a branch named "develop". `git branch develop`

Then start a new feature: `git feature start my-feature`

Work on your feature. Committing etc all you like. Then finally finish the feature and merge it back: `git feature finish my-feature`

The same start / finish functionality applies to the other tasks of git-flow.

```
git feature start <name>
git feature finish <name>
git release start <name>
git release finish <name>
git hotfix start <name>
git hotfix finish <name>
git support start <name>
git support finish <name>
```

### Why do this?

Not only does this not require any additional software. But it also doesn't require any middleware commands (ie `git !!FLOW!! release start <my-relase>`). Finally, you can put these alias's in a local repo, to enable "flow" only for that project.

Hopefully this improves your git workflow! :heart:

ps: If you're working in a production setting, you should [use the git-flow extension.](https://github.com/nvie/gitflow)

Please, those more experienced with git/bash than I, send pull requests / issues / comments!
