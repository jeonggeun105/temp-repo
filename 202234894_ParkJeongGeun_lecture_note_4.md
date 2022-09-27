# Lecture Note - Lab 4

### Run Shell
- Linux / MacOS : Search for "Terminal" in your apps and run it
- Windows : Install "Git Bash"

### Shell command

- pwd : shows the current path in a hierarchical directory
```sh
$ pwd
/c/Users/박정근
```

- cd : change directory
- ls : list files and directories

```sh
$ cd /c/Users/박정근/Desktop/Univ
$ pwd
/c/Users/박정근/Desktop/Univ

$ ls
'2022-2 학습공동체'/   '문제해결기법'/        '인성세미나'/ ...
```

cd arguments
> - / : root
> - . : current directory
> - .. : upper-level directory
> - ~ : home of current user
> - /[directory name] : absolute path
> - ./[directory name] : relative path
> - ../[directory name] : relative path

ls options
> - -l : show detailed information (long format)
> - -lh : same as above, **but size in units**

ls commands
> - ls : List the files in the working directory
> - ls /bin : List the files in the /bin direcoty 
> - ls -l : List the files in the working directory in long format
> - ls -l /etc /bin : List the files in the /bin directory and the /etc directory in long fomrat
> - ls -la .. : List all files (even ones with names beginning with a period character, which are normally hidden) in the parent of the working directory in long format

```sh
-rw-r--r-- 1 me me 44901 Sep  9 16:17 '코로나19 자진신고.pdf'
----------   -- -- ----- ------------ ---------------------
File         O  G  Size  Modification File Name
Permissions  w  r        Time
             n  o
             e  u
             r  p

```

- clear : clear shell

- cp : copy files and directories
> - cp file1 file2 : Copies the contents of file1 into file2. If file2 does not exist, It is created (overwrite)
> - cp -r dir1 dir2 : Copy the contents of the directory dir1. If directory dir2 does not exist, It is created ( dir1 is created within directory dir2 )
> - cp -i file1 file2 : If file2 exists, the user is prompted before it is overwritten with the contents of file1.
> - cp file1 dir1 : Copy the contents of file1 (into a file named file1) inside of directory dir1.

- mv : move files and directories or rename them
> - mv file1 file2 : If file2 does not exist, then file1 is renamed file2. **If file2 exists, its contents are silently replaced with the contents of file1.**
> - mv -i file1 file2 : If file2 exists, the user is prompted before it is overwritten with the contents of file1.
> - mv file1 file2 dir1 : The files file1 and file2 are moved to directory dir1. If dir1 does not exist, mv will exit with an error.
> - mv dir1 dir2 : If dir2 does not exist, then dir1 is renamed dir2. If dir2 exists, the directory dir1 is moved within directory dir2.

- rm : delete files and directories
> - rm file1 file2 : Delete file1 and file2
> - rm -i file1 file2 : the user is prompted before each file is deleted.
> - rm -r dir1 dir2 : Directories dir1 and dir2 are deleted along with all of their contents.

- mkdir : make a new directory
> * : All filenames ( *.txt )
> ? : Any filename followed by exactly ? more characters ( data???.txt )

- help : show help contents in shell
- man : show manual of command
- exit : exit terminal