# Lecture Note - Shell Commands

(Default) Standard output is screen.  

`>` : You can redirect output using this after a command (ls) to create and save the output in a file.
`>>` : append output to an existing file or create and write to a new file if it doesn't exist.

- cat : display the content of a text file.

```sh
ReJo@DESKTOP-SBC5KFR MINGW64 ~/Desktop
$ ls -lh > fl.txt

ReJo@DESKTOP-SBC5KFR MINGW64 ~/Desktop
$ cat fl.txt
total 1.3M
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:29 AIM/
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:57 Code/
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:29 Docu/
...

ReJo@DESKTOP-SBC5KFR MINGW64 ~/Desktop
$ ls -lh >> fl.txt

ReJo@DESKTOP-SBC5KFR MINGW64 ~/Desktop
$ cat fl.txt
total 1.3M
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:29 AIM/
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:57 Code/
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:29 Docu/
...
total 1.3M
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:29 AIM/
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:57 Code/
drwxr-xr-x 1 ReJo 197121    0 Oct  2 13:29 Docu/
...
```

`<` : You can redirect input from a file using this.

```
ReJo@DESKTOP-SBC5KFR MINGW64 ~/Desktop
$ cat in.txt
b
d
c
a
e
ReJo@DESKTOP-SBC5KFR MINGW64 ~/Desktop
$ sort < in.txt > out.txt

ReJo@DESKTOP-SBC5KFR MINGW64 ~/Desktop
$ cat out.txt
a
b
c
d
e
```

`|` : (Pipeline) feeds output of previous command to input of next command.  
command1 | command2 | command 3 : command1 output -> command2 input -> command2 output -> command3 input.  

`\` : (Backslash) can be used to ignore line change in command, to enter a long command in multiple lines.


Linux is a multi-user system.
Files and directories have a permission assigned differently to owner / group / others.

```sh
-rwxrwxrwx
       ___
Read, write, and execute permissions for all other users.
```
```sh
-rwxrwxrwx
    ___   
Read, write, and execute permissions for the group owner of the file.
```
```sh
-rwxrwxrwx
 ___      
Read, write, and execute permissions for the file owner.
```
```sh
-rwxrwxrwx
_
File type : - indicates regular file, d indicates directory
```

- chmod : changes permissions.
```sh
$ chmod 600 some_file
6 = 110 = rw- for owner
0 = 000 = --- for group
0 = 000 = --- for others
```
```
rwx rwx rwx = 111 111 111
rw- rw- rw- = 110 110 110
rwx --- --- = 111 000 000
...

rwx = 111 in binary = 7
rw- = 110 in binary = 6
r-x = 101 in binary = 5
r-- = 100 in binary = 4
```

- 777 (rwxrwxrwx) : No restrictions on permissions. Anybody may do anything. Generally not a desirable seeting.
- 755 (rwxr-xr-x) : The file's owner may read, write, and execute the file. All others may read and execute the file. This setting is common for programs that are used by all users.
- 700 (rwx------) : The file's owner may read, write, and execute the file. Nobody else has any rights. This setting is useful for programs that only the owner may use and must be kept private from other.
- 666 (rw-rw-rw-) : All users may read and write the file.
- 644 (rw-r--r--) : The owner may read and write a file, while all others may only read the file. A common setting for data files that everybody may read, but only the owner may change.
- 600 (rw-------) : The owner may read and write a file. All others have no rights. A common setting for data files that the owner wants to keep private.

Superuser : all system administation authorith. Some commands need superuser's privilleges.

- sudo : Put this before the command if you are a superuser. ( type exit to get out of a superuser session. )
- sudo -i : enter the root directory

- nano : write **a shell script**
- sh : run a shell script

- history : see previous command history or save it to a text file.

