### Cloning the Subversion Repository

### Contents

[TOC]

#### Clone the Subversion repository locally.

```bash
git svn clone <repo-url> --stdlayout --prefix svn/ -A authors.txt

# If the trunk/tags/branches are not standard
git svn clone <repo-url> --trunk=<trunk-folder> --branches=<branches-folder> --tags=<tags-folder>
```



#### Preserving ignored files

```bash
git svn show-ignore >> .gitignore
git add .gitignore
git commit -m "Convert svn:ignore properties to .gitignore"
```



#### Pushing to a local bare Git repository

```bash
mkdir \Repos\MyGitRepo.git
cd \Repos\MyGitRepo.git
git init --bare

git symbolic-ref HEAD refs/heads/trunk

# Add a bare remote pointing to the bare repository
cd \Sources\MySvnRepo
git remote add bare file:///c/Repos/MyGitRepo.git

# Push the local cloned repository to the new bare one
git push --all bare
```

We have a brand new bare repository that is a perfect copy of the original Subversion one.



#### Arrange branches and tags

```bash
# /trunk ==> /master 
git branch -m trunk master
```



#### Converting Subversion tags to Git tags

```bash
git for-each-ref --format='%(refname)' refs/heads/tags |
cut -d / -f 4 |
while read ref
do
  git tag "$ref" "refs/heads/tags/$ref";
  git branch -D "tags/$ref";
done
```



#### Pushing the local repository to a remote

Ready to be pushed to a remote server. The result of the conversion is a full Git repository, where branches, tags, and commit history have been preserved.
