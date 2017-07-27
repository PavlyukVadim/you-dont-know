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

# Show Git Branch In Terminal – Command Prompt
Open the ~/.bashrc file with your favorite text editor and add the following lines:
```
git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
export PS1="[\u@\h \W]\[\033[00;32m\]\$(git_branch)\[\033[00m\]\$ "
```
Load the ~/.bashrc to apply changes:
```
source ~/.bashrc
```
