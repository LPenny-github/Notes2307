# sudo


## basic knowledge

1. a command that can operate **like** root

2. only the user who has administrator privileges can use `sudo`

    * how to check if the user has administrator privileges
        
        * list all members in `admin` group

            open the terminal:
            
            ```bash
            dscl . read /groups/admin | grep GroupMembership 
            ``` 

            expected output:

            ```bash
            GroupMembership: root adm
            ```
            
            it shows only `root` and `adm` have administrator privileges in this computer

        * check out `id`

            open the terminal:
            
            ```bash
            dscl . read /groups/admin | grep PrimaryGroupID 
            ``` 

            expected output:

            ```bash
            PrimaryGroupID: 80
            ```

            check out if this user is in `admin`(No. 80) group:

            ```bash
            id
            ```

3. read the user manual of `sudo`

    open the terminal:

    ```bash
    man sudo
    ```


## root in macOS

1. default off

2. can do a lot of things to damage your computer

3. recommend not to use it (use `sudo` instead)

4. how to sign in as `root`

    * read the official documentation first

        * 如何在 Mac 上啟用 root 使用者或更改 root 密碼
            * https://support.apple.com/zh-tw/HT204012


## reference

* 如何在 Mac 上啟用 root 使用者或更改 root 密碼
    * https://support.apple.com/zh-tw/HT204012  