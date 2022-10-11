# Lecture Note - Git Commands

### Installing Git
- Linux / Mac / Windows (check pre-installed version)
```sh
$ git --version
git version 2.25.1
```

- Linux (install on a Debian-based distribution)
```sh
$ sudo apt install git-all
```
- Mac 
https://git-scm.com/download/mac
- Windows - Run "Git Bash"
https://git-scm.com/download/win

### Git configuration levels
1. System level: --system option. Affects all users and repositories on the system (administrative)
`file: /etc/gitconfig`
2. Global (user) level: --global option. Affects all repositories of a current user
`file: ~/.config/git/config`
3. Local level: --local option. Specific to the current repository
`file: .git/gitconfig`

Each level overrides values in the previous level: system -> global -> local
```sh
$ git config --list
$ git config --list --show-origin
```

```sh
$ git config --global user.name "JeongGeun Park"
$ git config --global user.email jhiran1897@gmail.com
$ git config --glboal init.defaultBranch main
```

- $ git init  
Initialize a repository in an existing directory.
```sh
$ git init
Initialized empty Git repository in ~
```

- $ git status  
Check repository status
```sh
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed) 
        Python/.cph/
        Python/pra.py

nothing added to commit but untracked files present (use "git add" to track)
```

- $ git add (file_name)  
Add a new file to be staged (tracked)
```sh
$ git add Python/pra.py

$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Python/pra.py

Untracked files:
  (use "git add <file>..." to include in what will be committed) 
        Python/.cph/
```

if you use nano commands for editing, git status tell you **change not staged for commit**.


- $ git add .  
Add all files to be staged (tracked)
```sh
$ git add .

$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Python/.cph/.pra.py_9c8486ce08e6665d0708f580285616a4.prob
        new file:   Python/pra.py
```

- $ git rm --cached (file_name)  
Unstage a file
```sh
$ git rm --cached Python/pra.py
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Python/.cph/.pra.py_9c8486ce08e6665d0708f580285616a4.prob

Untracked files:
  (use "git add <file>..." to include in what will be committed) 
        Python/pra.py
```

- .gitignore (Ignoring a file)  
```
# ignore all .a files
*.a

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in any directory named build
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf
```

- $ git commit -m "commit message"
```sh
$ git commit -m "Update status"
[master 7c1f9bd] Update status
 2 files changed, 14 insertions(+)
 create mode 100644 Python/.cph/.pra.py_9c8486ce08e6665d0708f580285616a4.prob
 create mode 100644 Python/pra.py
```

- $ git log  
- $ git branch  
Show branch list
- $ git branch -m (first name) (second name)  
Change branch name (first name) to (second name)
