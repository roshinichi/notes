# 12/28/14

***

- `cat ~/.profile > ~/.zshrc` **_copy > paste_**
-  `cat` **_displays a file_**
-  `.` **_hidden file_**
- with `/`prefix : **_absolute dir_**
- w/o `/`prefix : **_relative dir_**
- `/` postfix: as a directory
- `zsh` a shell, a better bash
- `zshrc` rc: **_runtime environment configuration, differed from `root` and `user`, 2 configs_**
- system's zshrc is located in `/etc/zshrc` (configs are put in etc folder)
- user's zshrc is located in `~/.zshrc` (hiddle file)
- `chmod`**_every file has permission, use this to change a file's privilege_** 

- `Al` A : all files (including hidden files) l:list- 
- `alias` define commands (xx == xx)
- `man ls` displays commands menu of ls

```
chmod 666 filename.xx
chmod u+x filename.xx
chmod -R u+x dir
```

- 'drwxr' d:directory rwx:read write execute w/o x cannot execute

##Check system privilege

- 1st rwx: user 
- 2nd rwx: staff(group/username) 
- 3rd rwx: everyone
- numbers:binary sum

```
r,4,100
w,2,010
x,1,001
nothing,0,000
```
- sum is 4+2+1=7
- 6 = 4+2 (r w)
- 5 = 4+1 (r x)
- i.e. 666 == rwrwrw
- i.e. 777 == rwxrwxrwx
- most common: 644 & 755 (5 ==`cd`able)
- `./xxx.sh` if "permission denied" == not executable (rw)
- check permission with `ll`
- filename `cups` is related to printer service
- `root` system user
- `wheel`system group
***

- subl xxx.sh **_sh==shell_**