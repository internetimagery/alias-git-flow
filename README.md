# Super Simple Git Flow!

This method adds some commands to follow the excellent [git flow methodology](http://nvie.com/posts/a-successful-git-branching-model/) using simple git aliases.

To use them, simply add the text from the "config" file in this repo to your own git config.

To use git flow. Ensure you first have a branch named "develop".

Then start a new feature:

```
git feature start my-feature
```

Work on your feature. Committing etc all you like. Then finally finish the feature and merge it back:

```
git feature finish my-feature
```

The same start / finish functionality applies to the other tasks of git-flow.

```
git release start
git release finish
git hotfix start
git hotfix finish
git support start
git support finish
```
