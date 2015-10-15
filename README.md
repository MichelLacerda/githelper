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
$ git push origin --delete <branchName>

or

$git push origin :<branchName>
```
