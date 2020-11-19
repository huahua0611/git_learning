# Git Learning

## Introduction

This repository is about my git learning, and I follow the instructor from [time.geekbang.org](https://time.geekbang.org/course/intro/100021601).

The basic website framework comes from [https://github.com/git201901/git_learning](https://github.com/git201901/git_learning).

This is my [Github Pages](https://qzjqt76zfqzx.github.io/git_learning/) of this repository. It is created by myself not follow above framework.

This is a very nice [BOOK](https://git-scm.com/book/en/v2) for git

This is the important reference [Git Reference Manual](https://git-scm.com/docs).

This is the official [Git Cheat Sheets](https://training.github.com/)

## Content

### Setup and Config

#### Install git

You may find the link to install git from [Git Download](https://git-scm.com/downloads).

After you install, run command in your terminal

```bash
git --version
```

then you should get

```bash
git version X.XX.X  //right now is 2.29.2
```

If you have any question or you need any help then you can run

```bash
git --help
```

or

```bash
man git
```

or go to [https://git-scm.com/doc](https://git-scm.com/doc) to find the result. However I prefer [Git Reference Manual](https://git-scm.com/docs) which as same as `man git`.

#### git config

run `git config` in terminal you will get

```bash
usage: git config [<options>]

Config file location
    --global              use global config file
    --system              use system config file
    --local               use repository config file
    --worktree            use per-worktree config file
    -f, --file <file>     use given config file
    --blob <blob-id>      read config from given blob object

Action
    --get                 get value: name [value-regex]
    --get-all             get all values: key [value-regex]
    --get-regexp          get values for regexp: name-regex [value-regex]
    --get-urlmatch        get value specific for the URL: section[.var] URL
    --replace-all         replace all matching variables: name value [value_regex]
    --add                 add a new variable: name value
    --unset               remove a variable: name [value-regex]
    --unset-all           remove all matches: name [value-regex]
    --rename-section      rename section: old-name new-name
    --remove-section      remove a section: name
    -l, --list            list all
    -e, --edit            open an editor
    --get-color           find the color configured: slot [default]
    --get-colorbool       find the color setting: slot [stdout-is-tty]

Type
    -t, --type <>         value is given this type
    --bool                value is "true" or "false"
    --int                 value is decimal number
    --bool-or-int         value is --bool or --int
    --path                value is a path (file or directory name)
    --expiry-date         value is an expiry date

Other
    -z, --null            terminate values with NUL byte
    --name-only           show variable names only
    --includes            respect include directives on lookup
    --show-origin         show origin of config (file, standard input, blob, command line)
    --show-scope          show scope of config (worktree, local, global, system, command)
    --default <value>     with --get, use default value when missing entry

```

Firstly, you can see that "System, Global and Local". Although there has "worktree", "worktree" is similar with "local" but they are not same. Both "lcoal" and "worktree" normally should point to the same repository.

Then there could be three place to store your git config.

1. `[path]/etc/gitconfig file`: Contains values applied to every user on the system and all their repositories.
2. `~/.gitconfig` or `~/.config/git/config` file: Values specific personally to you, the user to all repositories under direction of `echo ~`.
3. `config` in all git repositories like `.git/config`: Values only applied to each itself repository.

Make sure each time calling `git config` with the scope.

Normally, we set the confifg for `--global`, then all repositories under USER_DIR will use same config. Also there are two ways can set or change config. First one is using command, and second one edit the config file.

Those are two examples.

Before doing example, run `git config --global --list`, there should no output about `user.name` and `user.email` if you are first time install git and use.

Example 1 - Change by Command

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

you may run

```bash
git config --global --list
```

or

```bash
git config --global user.name
git config --global user.email
```

to check the new setting.

Example 2 - edit in config

```bash
cd ~
vi vi ~/.gitconfig
```

you should get

```bash
[user]
        name = John Doe
        email = johndoe@example.com
```

above information should as same as you type in example 1, and now you may change it again. edit and save, then run `git config --global --list` to see your change.

Here is a new feature `--show-origin` to find where is the attributes come from?

```bash
git config --global --list --show-origin
```

you will see the config dir with the attributes.

This output is print under one repository direction.

```bash
file:/MY/USER/NAME/.gitconfig      user.name=******
file:/MY/USER/NAME/.gitconfig      user.email=******
file:.git/config        ******
file:.git/config        ******
```

---

## branch rules (setting/branches)

- requires code review
- requires liner history (rebase)
- include admins follow the rules
- disable push -f

## Contents

### Unit 1

1.4 git init and setting local git config

- git init
- git config --local (check local git config and setting)

  1.5 basic knowledge about local work space, cached and HEAD

  1.6 rename file and delete file

  1.7 using git log to check git history change

  1.8 using gitk to check git history change

  1.9 .git structure

  1.10 the relationship between commit, tree and blob

  1.11 practice about 1.10

  1.12 head detached

  1.13 deep understanding about head detached

### Unit 4

learning git work with multiple people

4.1 diff people work on diff file by same branch

4.2 diff people work on same file with diff part

- change from web by first client
- change from remote git by second client, add something

  4.3 diff people work on same file on same part

- change the same file at same part by two client, the later pusher will face conflict

  4.4 diff people work on same file and one rename others face conflict

- change the practice_file to practice_file_v4.4
- others add line 6 to practice_file
- fetch and merge face problem

  4.5 diff rename the same file

- change practice_file name by web and remote
- git will create two new file with each name and remove the original one
- people need to discuss about the name of rename file !!!

### Unit 5

5.1 never use git push -f (force push) to remote git

5.2 never rebase remote git

### Unit 6

6.1 why github is popular
