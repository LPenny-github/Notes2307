# 3. how to stop the window popping up

## purpose

reduce the same operation from daily to **zero**

## description

As a standard user named `dev`, not part of _developer, I have to fill the informarion in the form when I run the code at first time.

## what & why

same as before

## how

Let `dev` join `_developer` group.

1. change the setting

    open the terminal as administrator:
    
    ```bash
    sudo dscl . append /Groups/_developer GroupMembership dev
    ```

    * `sudo`: superuser do
    * `dscl . `: Creates, reads, and manage Directory Service data.
    * `append`: Appends one or more val to key in record_path. The property is created if it does not exist.

1. system will need administrator's password to execute the command

1. double check if `dev` is in `_developer`(No. 204) group

    open the terminal as `dev`:

    ```bash
    id
    ```

## test

reopen Xcode and run the same project

## reference

* Stop "developer tools access needs to take control of another process for debugging to continue" alert
    * https://stackoverflow.com/questions/9132826/stop-developer-tools-access-needs-to-take-control-of-another-process-for-debugg

* Developer tools group
    * https://developer.apple.com/forums/thread/44758

* dscl: directory services command line
    * https://www.real-world-systems.com/docs/dslocal.db.html?fbclid=IwAR1r-tmVK98fvE_FPr3TwkU34yqGjNZv9RBfAmqvlT4PXBBYgTS7jm0QzPU