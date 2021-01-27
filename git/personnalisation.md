# Personnalisation

## Mes alias

```text
graph = log --graph --pretty=format:'%C(yellow)%h%C(cyan)%d%Creset %s => %C(green)%an%C(white), %C(red)%ar%Creset'
adog = log --all --decorate --oneline --graph
lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
amend = commit --amend
ci = commit
co = checkout
st = status
br = branch
mr = !sh -c 'git fetch $1 merge-requests/$2/head:mr-$1-$2 && git checkout mr-$1-$2' -
```

