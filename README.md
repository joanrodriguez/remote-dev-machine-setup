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
- Get Yarn `npm install --global yarn`

## Increase max size of watchers for VSCode

The current limit can be viewed by running:

`cat /proc/sys/fs/inotify/max_user_watches`

The limit can be increased to its maximum by editing `/etc/sysctl.conf` (except on Arch Linux, read below) and adding this line to the end of the file: `fs.inotify.max_user_watches=524288`

The new value can then be loaded in by running `sudo sysctl -p.

## Install docker and docker-compose

Please refer to the official guides.

## Install Eslint globally
- Because we are opening the root of the multi-repo with VScode, it cannot detect Eslint from the `node_modules`.
- Therefore, install it locally

## Install Hasura Cli
- curl -L https://github.com/hasura/graphql-engine/raw/stable/cli/get.sh | bash
