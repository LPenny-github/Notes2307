# 1. find the right info to fill in the form

## purpose

find the right information (username & password)

## description

When I, a standard user, run my code in Xcode, a window pops up asking me to fill some information in.

The full text is as follows:

```text
Developer Tools Access

Developer Tools Access needs to take control of another process for debugging to continue.

Enter the name and password of a user in the "Developer Tools" group to allow this.
```

## what and why

1. System needs your confirm to run the code, because it's risky behavior.

1. This user may not be in the developer group, but the administrator in the computer may be. 

## how

open the terminal:

1. get the serial number of the group

    ```bash
    cat /etc/group
    ```

    what I am looking for:

    ```bash
    _developer:*:204:
    ```

1. check out if this user is in `_developer` (NO. 204)

    ```bash
    id
    ```

    this command will list the groups which the user has joined

open the terminal as administrator(optional):

1. check out if administrator is in `_developer` (NO. 204)

    ```bash
    id
    ```

fill the username and password if it is in `_developer` group and Xcode will run the code

## test

none

## reference

* Stop "developer tools access needs to take control of another process for debugging to continue" alert
    * https://stackoverflow.com/questions/9132826/stop-developer-tools-access-needs-to-take-control-of-another-process-for-debugg


