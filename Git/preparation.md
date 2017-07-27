# Preparation
Setting up name and e-mail address:
```
git config --global user.name "Your Name"
git config --global user.email "your_email@whatever.com"
```
# Common aliases
Add the following to the .gitconfig file in your $HOME directory:
```
[alias]
  co = checkout
  ci = commit
  st = status
  br = branch
  hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
  type = cat-file -t
  dump = cat-file -p
```
