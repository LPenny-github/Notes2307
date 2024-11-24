# how to generate ssh key

* open `Terminal`
* `ssh-keygen -t ed25519 -C "youremail@mail.com"` 

## test

### make sure ssh key was generated successfully

* open `Terminal`
* `ls -al ~/.ssh` 

### make sure connect throught ssh key successfully

* open `Terminal`
* `ssh -T git@github.com` 

