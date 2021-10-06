# remote-dev-machine-setup
A walkthrough to setting-up a new dev machine


`sudo apt-get update`

`sudo apt-get install zsh`

`sudo chsh -s $(which zsh) $(whoami)`

If this fails with `chsh: PAM: Authentication failure`, you may want to edit `/etc/pam.d/chsh` changing
`auth       required   pam_shells.so`
to
`auth       sufficient   pam_shells.so`


Start a new session and check that you are using zsh as your default shell

`echo $0`

## Configure git

`git config --global user.email "rodriguezjoan@gmail.com"`
`git config --global user.name "Joan Rodriguez"`


## Install Oh My Zsh

Add useful plugins by editing `~/.zshrc`:

```
plugins=(zsh-syntax-highlighting zsh-autosuggestions history-substring-search alias-finder brew common-aliases copydir copyfile docker docker-compose encode64 extract git jira jsontools node npm osx urltools vi-mode vscode web-search z)
```

Two of them must be installed:

```
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

## Get node
- Install nvm
- Use it to install node `nvm install node`
