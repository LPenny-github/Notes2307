# Make sure you configure your “user.name” and “user.email” in git

## expectation

use the vscode GUI to execute `git commit` successfully

## description

When I used `git commit` at the first time by the vscode GUI and also in this computer, a warning window showed up:

```text
Make sure you configure your “user.name” and “user.email” in git.
```

If I click the `Open Git Log` buttom, the output pane showed:

(This is only one part of the log.)

```text
2023-07-31 14:00:00.847 [info] Author identity unknown
*** Please tell me who you are.
Run
  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"
to set your account's default identity.
Omit --global to set the identity only in this repository.
fatal: no email was given and auto-detection is disabled
```

## what & why

* `write` requires more permissions than `read`. That's why you don't have to set `user.name` and `user.email` when you use `git pull` or `git clone`.

## how 

In your vscode terminal:

(If you only use this setting in this project, please omit `--global`.)

```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

double check to make sure you did it right:

```bash
git config user.name
```

```bash
git config user.email
```

## test

execute `git commit` again regardless of whether you choose to use the vscode GUI or the vscode terminal

## reference

* 1.6 Getting Started - First-Time Git Setup
    * https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup