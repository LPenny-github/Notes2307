# 2. how to reduce the number of times to fill in the form

## purpose

**reduce** the same operation 

## description

As a standard user, not part of _developer, I have to fill the informarion in the form every single time, when I want to run the code.

## what & why

same as before

## how 

open the terminal:

1. check out the setting
    
    ```bash
    DevToolsSecurity --status
    ```

2. enable

    ```bash
    DevToolsSecurity --enable
    ```

## test

reopen Xcode and run the same project

## reference

* Stop "developer tools access needs to take control of another process for debugging to continue" alert
    * https://stackoverflow.com/questions/9132826/stop-developer-tools-access-needs-to-take-control-of-another-process-for-debugg