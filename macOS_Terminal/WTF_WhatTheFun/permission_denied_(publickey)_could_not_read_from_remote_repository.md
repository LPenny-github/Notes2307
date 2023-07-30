# git@github.com: Permission denied (publickey). fatal: Could not read from remote repository.

## expectation

clone the repo successfully by using

```bash
git clone <ssh url>
```

## description

I opened Terminal and entered the command: 

```bash
git clone git@github.com:LPenny-github/Notes2307.git
```

It failed with the error message: 

```text
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
Please make sure you have the correct access rights
and the repository exists.
```

## what & why

github didn't know who you are

## how

1. check out whether you have generated ssh keys or not
    * if you have generated ssh keys, you can go directly to step 3.
    * if you don't have any ssh key, follow step 2.

    ```bash
    ls ~/.ssh
    ```

1. generate ssh keys
    * you can add the passphrase on the ssh keys, or change the passphrase later
        * see more: Working with SSH key passphrases
            * https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases 

    ```bash
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```
    * -t <algorithm>: choose the way generates your ssh keys
    * -C: command

1. copy your public ssh key and add in your github account

    * (1) copy your public ssh key:

        (the file name is default.)

        ```bash
        pbcopy < ~/.ssh/id_ed25519.pub
        ```

    * (2) add it into your github account:
        * docs: Adding a new SSH key to your GitHub account
            * https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

## test

do it again: 

```bash
git clone git@github.com:LPenny-github/Notes2307.git
```

## reference

* Generating a new SSH key and adding it to the ssh-agent
    * https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

* Adding a new SSH key to your GitHub account
    * https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

* Working with SSH key passphrases
    * https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases 

