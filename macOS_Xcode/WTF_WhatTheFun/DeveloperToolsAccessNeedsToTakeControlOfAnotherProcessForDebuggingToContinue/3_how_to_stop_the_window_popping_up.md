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
    sudo dscl . append /groups/_developer GroupMembership dev
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

* reopen Xcode and run the same project

* double check if `dev` is in `_developer`(No. 204) group (optional)

    open the terminal as `dev`:

    ```bash
    dscl . read /groups/_developer | grep GroupMembership
    ```

    * `read`: Displays (case insentitive) directory properties.
    * `|`: forward the output data of one instruction to the input data of another instruction
    * `grep <keyword>`: searche for lines of text that contains the keyword

    expected output:

    ```bash
    GroupMembership: dev
    ```

## reference

* Stop "developer tools access needs to take control of another process for debugging to continue" alert
    * https://stackoverflow.com/questions/9132826/stop-developer-tools-access-needs-to-take-control-of-another-process-for-debugg

* Developer tools group
    * https://developer.apple.com/forums/thread/44758

* dscl: directory services command line
    * https://www.real-world-systems.com/docs/dslocal.db.html

* 在 Mac 上轉址「終端機」輸入和輸出
    * https://support.apple.com/zh-tw/guide/terminal/apd1dbe647b-7e11-49dc-aa76-89aa7e53ce36/2.13/mac/13.0