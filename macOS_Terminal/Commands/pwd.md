# pwd (print working directory)

## what

```
return working directory name
```

## options

```
The options are as follows:

     -L      Display the logical current working directory.

     -P      Display the physical current working directory (all symbolic
             links resolved).

     If no options are specified, the -L option is assumed.
```

### 比喻範例

資料結構：
```
        root 裡面有三個物件

                fruit(link to apple)
                apple(folder)
                banana(folder)
```

情境一：
```bash
cd root/fruit
pwd -L  
# /root/fruit
``` 

情境二：
```bash
cd root/fruit
pwd -P 
# /root/apple
``` 

---

#### 還不知道如何應用的知識

link 有 soft link 和 hard link 兩種。當刪除 soft link 時，只會刪除 soft link ；當刪除 hard link 時，hard link 指向的物件也會被刪除。 

---

## why isn't the Terminal designed to display the absolute path by default?

for better readability (by limiting the information in the pane)

## reference

* Terminal `man pwd`

* 第六章、Linux 檔案與目錄管理
        https://linux.vbird.org/linux_basic/centos7/0220filemanager.php#dir_opdir
