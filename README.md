this is the GIT KATA : 3-way merge 

The task
You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.

Create a branch called greeting and switch to it
Edit the greeting.txt to contain your favorite greeting
Add greeting.txt files to the staging area
Commit
Switch back to the master branch
Create a file README.md with information about this repository
Add the README.md file to staging area and make the commit
What is the output of git log --oneline --graph --all?
Diff the branches
Merge the greeting branch into master
What is the output of git log --oneline --graph --all now? Observe the extra merge commit created with the message "Merge branch 'greeting'".


///////////////////////////////////////////////////////////
THIS IS COMMANDS EXECUTION
//////////////////////////////////////////////////////////

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git init
Initialized empty Git repository in C:/Users/Manan Bhateja/Desktop/kattas/kattas5/.git/

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ vi greeting.txt

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git add .
warning: LF will be replaced by CRLF in greeting.txt.
The file will have its original line endings in your working directory

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git commit -m "first"
[master (root-commit) 1801319] first
 1 file changed, 1 insertion(+)
 create mode 100644 greeting.txt

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git branch new

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git branch
* master
  new

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git switch new
Switched to branch 'new'

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (new)
$ git branch -m greeting

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (greeting)
$ git branch
* greeting
  master

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (greeting)
$ vi greeting.txt

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (greeting)
$ git add greeting.txt
warning: LF will be replaced by CRLF in greeting.txt.
The file will have its original line endings in your working directory

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (greeting)
$ git commit -m "greetings added"
[greeting d8d1c36] greetings added
 1 file changed, 3 insertions(+)

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (greeting)
$ git status
On branch greeting
nothing to commit, working tree clean

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (greeting)
$ ls
greeting.txt

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (greeting)
$ git switch master
Switched to branch 'master'

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ vi README.md

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git add .
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git commit -m "added readme"
[master 094fe9b] added readme
 1 file changed, 17 insertions(+)
 create mode 100644 README.md

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git log --oneline --graph --all
* 094fe9b (HEAD -> master) added readme
| * d8d1c36 (greeting) greetings added
|/
* 1801319 first

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git diff master greeting
diff --git a/README.md b/README.md
deleted file mode 100644
index 457848a..0000000
--- a/README.md
+++ /dev/null
@@ -1,17 +0,0 @@
-this is the GIT KATA : 3-way merge
-
-The task
-You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.
-
-Create a branch called greeting and switch to it
-Edit the greeting.txt to contain your favorite greeting
-Add greeting.txt files to the staging area
-Commit
-Switch back to the master branch
-Create a file README.md with information about this repository
-Add the README.md file to staging area and make the commit
-What is the output of git log --oneline --graph --all?
-Diff the branches
-Merge the greeting branch into master
-What is the output of git log --oneline --graph --all now? Observe the extra merge commit created with the message "Merge branch 'greeting'".
-
diff --git a/greeting.txt b/greeting.txt
index fd086bc..98e7dea 100644
--- a/greeting.txt
+++ b/greeting.txt
@@ -1 +1,4 @@
 this is greeting card
+
+Hello and welcome to this repo
+have a nice day

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git diff greeting master
diff --git a/README.md b/README.md
new file mode 100644
index 0000000..457848a
--- /dev/null
+++ b/README.md
@@ -0,0 +1,17 @@
+this is the GIT KATA : 3-way merge
+
+The task
+You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.
+
+Create a branch called greeting and switch to it
+Edit the greeting.txt to contain your favorite greeting
+Add greeting.txt files to the staging area
+Commit
+Switch back to the master branch
+Create a file README.md with information about this repository
+Add the README.md file to staging area and make the commit
+What is the output of git log --oneline --graph --all?
+Diff the branches
+Merge the greeting branch into master
+What is the output of git log --oneline --graph --all now? Observe the extra merge commit created with the message "Merge branch 'greeting'".
+
diff --git a/greeting.txt b/greeting.txt
index 98e7dea..fd086bc 100644
--- a/greeting.txt
+++ b/greeting.txt
@@ -1,4 +1 @@
 this is greeting card
-
-Hello and welcome to this repo
-have a nice day

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git log --oneline --graph --all
* 094fe9b (HEAD -> master) added readme
| * d8d1c36 (greeting) greetings added
|/
* 1801319 first

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git merge greeting
Merge made by the 'ort' strategy.
 greeting.txt | 3 +++
 1 file changed, 3 insertions(+)

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git status
On branch master
nothing to commit, working tree clean

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git log --oneline --graph --all
*   e0b19c9 (HEAD -> master) Merge branch 'greeting' Merge branch greeting
|\
| * d8d1c36 (greeting) greetings added
* | 094fe9b added readme
|/
* 1801319 first

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git log --oneline --graph
*   e0b19c9 (HEAD -> master) Merge branch 'greeting' Merge branch greeting
|\
| * d8d1c36 (greeting) greetings added
* | 094fe9b added readme
|/
* 1801319 first

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git log --oneline
e0b19c9 (HEAD -> master) Merge branch 'greeting' Merge branch greeting
094fe9b added readme
d8d1c36 (greeting) greetings added
1801319 first

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git remote add origin git@github.com:manan23bhateja/katas5.git

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git remote
origin

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git push -u origin master
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (11/11), 1.36 KiB | 115.00 KiB/s, done.
Total 11 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To github.com:manan23bhateja/katas5.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean

Manan Bhateja@LAPTOP-LI3D2LTR MINGW64 ~/Desktop/kattas/kattas5 (master)
$

