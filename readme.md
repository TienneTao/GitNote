## git commands

[TOC]



```sh
git --help
git <command> --help
```



##### Setting up a new repository: git init

Create a `.git` subfolder. If delete it or modify files inside by hand, you could get into trouble.

##### Adding a file: git add

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

git log
