# git_learning

[https://github.com/git201901/git_learning](https://github.com/git201901/git_learning)

---

## branch rules (setting/branches)

- requires code review
- requires liner history (rebase)
- include admins follow the rules
- disable push -f

## Contents

### Unit 1

git base

1.1 basic describe about git

1.2 install git

- download from [git](https://git-scm.com/downloads)

  1.3 git config before using git

- git config -l --global/--local/--system
- git config user.name
- git config user.email

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
