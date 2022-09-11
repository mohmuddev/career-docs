---
sidebar_position: 1
---

# Toturial - Git

## Git get started
Git is a DevOps tool used for source code management. It is a free and open-source version control system used to handle small to very large projects efficiently. Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development.

#### Configure Git
Now let Git know who you are. This is important for version control systems, as each Git commit uses this information:

```shell 
git config --global user.name "mohmuddev"
git config --global user.email "mohamud@gmail.om"
```

:::note  
Use global to set the username and e-mail for every repository on your computer.
If you want to set the username/e-mail for just the current repo, you can remove global
:::

#### Create git folder
Create a new folder for our project:
```shell
mkdir myproject
cd myproject
```

#### Initialize Git
```shell
git init 
Initialized empty Git repository in /Users/user/myproject/.git/
```

```shell
git status
On branch master

No commits yet

Untracked files:
(use "git add ..." to include in what will be committed)
index.html

nothing added to commit but untracked files present (use "git add" to track)
```

#### Add files under folder
```shell
git add --all "Short command" git add -a
```

#### Git commit
```shell title="new commit"
git commit -m "First commit"
```

```shell title="update commit"
git commit -a -m "updated first commit"
```
