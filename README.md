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
