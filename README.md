# githelper
Arquivos para auxiliar

GitLog
```sh
ref: http://stackoverflow.com/questions/1057564/pretty-git-branch-graphs

$ vim ~/.gitconfig

[alias]
lg1 = log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
lg2 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''%C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all
lg = !"git lg1"

How to use:
$ git lg
$ git lg1
```

or

```sh
$ git log --graph --abbrev-commit --decorate --date=relative --all
$ git log --graph --oneline --decorate --date=relative --all
```

#### Remove remote Branch 

```sh
git 1.7+ $ git push origin --delete <branchName>
git 1.7- $git push origin :<branchName>
```

#### Remove local branch
```sh
[Full]  $ git branch --delete <branch>
[Short] $ git branch -d <branch>
[Force  $ git branch -D <branch>

```


####  Revert commit
```sh
$ git reset --hard HEAD

or

$ git reset --hard <HASH: e3a3df4>
------> git reset --hard e3a3df4
```


#### Git status date
```sh
$ git status -s | while read mode file; do echo $mode $(date --reference=$file +"%Y-%m-%d %H:%M:%S") $file; done
```

#### Rename branch local/remote
```sh
$ git branch -m old_branch new_branch         # Rename branch locally    
$ git push origin :old_branch                 # Delete the old branch    
$ git push --set-upstream origin new_branch   # Push the new branch, set local branch to track the new remote

```

```sh

teste = git diff --name-only {src} {comp} HEAD
git archive --format=tar.gz -o {nameoutput}.tar.gz HEAD $teste


git diff --name-only -z --diff-filter=ACMRT master..HEAD | xargs -0 git archive -o diff_archive.zip HEAD --

files=$(git diff --name-only master..HEAD)
git archive --format=zip -o diff_archive.zip HEAD ${files:-NO_SUCH_FILE}
```
