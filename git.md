## Table of Contents

  1. [Preparation](#preparation)
  1. [Show Git Branch In Terminal](#show-git-branch-in-terminal)
  
## Preparation

  <a name="preparation"></a><a name="1.1"></a>
  - [1.1](#preparation) **Preparation**: 
    Setting up name and e-mail address:
    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "your_email@whatever.com"
    ```

<a name="common--aliases"></a><a name="1.2"></a>
  - [1.2](#common--aliases) **Common aliases**:
Add the following to the .gitconfig file in your $HOME directory:
    ```bash
    [alias]
      co = checkout
      ci = commit
      st = status
      br = branch
      hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
      type = cat-file -t
      dump = cat-file -p
    ```

**[⬆ back to top](#table-of-contents)**

## Show Git Branch In Terminal

Open the ~/.bashrc file with your favorite text editor and add the following lines:

```bash
git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
export PS1="[\u@\h \W]\[\033[00;32m\]\$(git_branch)\[\033[00m\]\$ "
```

Load the ~/.bashrc to apply changes:

```bash
source ~/.bashrc
```

**[⬆ back to top](#table-of-contents)**

