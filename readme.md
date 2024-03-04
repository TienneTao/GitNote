## git commands

[TOC]



```sh
git --help
git <command> --help
```



##### Setting up a new repository: git init

Create a `.git` subfolder. If delete it or modify files inside by hand, you could get into trouble.

##### Adding a file: git add
```sh
git add --all(-A)
git add *.txt

# Ignore some files and folders by default
.gitignore

# Add a file in the .gitignore file even if it is marked to be ignored
git add -f(--force)
```

The `git add` command tells Git that we want it to take care of that file and check it for future modifications.

##### Check the status of the repo: git status

```sh
git status
```

##### Commit the added files: git commit

> git commit --message(-m)
>
> git commit

```sh
git commit --message "tienne's notes :)"
```



untracked, added(unmodified > modified), staging area(index)

##### Unstaging a file: git reset/rm

Back the file in the untracked status.

```sh
git reset HEAD <file>

# Go back to the initial state, losing all the changes we made in the working directory.
git reset --hard HEAD 
```

If you use the `git rm` command on an already committed file, you actually mark it for deletion. The next commit will delete it.

```sh
git rm --cached <file or folder>
```



git reset
git rm

```sh
git log
git log --graph --decorate --pretty=online --abbrev-commit
git config --global alias.tree 'log --graph --decorate --pretty=onelinw --abbrev-commit'
```

##### Highlighting an important commit -- Git tags
Mark a commit with a tag to place a milestone in our repository.
```sh
git tag -a <tag name>
git tag -a MyTagName -m "This is tienne's first tag :)"
```

##### Looking at the current branches
```sh
git branch
# Creat a new branch
git branch TienneNewBranch
# Switching from branch to branch
git checkout TienneNewBranch

```


