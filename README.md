*Just some logs of this file*

The Very beginning
===================

This is just a test.

I set up GitHub and download Git just now, at around 3:23 pm AZ time, Nov 7, 2013.

I have not figured out how to use it yet.

3:43 pm: this will be from local work dir.

Some new work
====================

Now is 2020-04-17 Friday 4:19 pm MST

I've setup Visual Studio Code (VSC) for C++ and Python dev, and installed VSC extensions of remote dev using MSL and CMake for multi-file C++ dev.

I've refreshed my C++ knowledge and Git knowledge.

I'm doing all these things right now.

The commands I learned/refreshed today. (All command are on local machine)
- *Initial important config* (only run once)
    * `git config --global user.name "my full name"`
    * `git config --global user.email my_email@my_server`
    * show config and its origin! `git config --list --show-origin`
- *New repo* Create a new dir, enter, and do `git init`, then do some work
- `git add/rm ...` to modify files 
- `git commit -a` to commit all content changes
- *Clone a repo* 
    * `git clone https://github.com/zhbbz/z1.git` (a local z1/ dir will be created in current folder)
    * `git clone https://github.com/zhbbz/z1.git myrepo` (a local myrepo/ dir will be created in current folder)
- *Push to online repo* 
    * `git push origin master`
- *Pull to local* 
    * `git pull origin master`

Good luck for my job huntings!

today is Sun 04/19/2020.

New Again (as of 2023-06-06)
============================

Can you believe it?!

Yet another new refreshment of Git knowledge in June 2023

(OMG, I'm 50 years old now!!!)

* My daily addition at 2023-06-07 Wed
* 06/09 Fri: Realized that I never finished chapter 5 of [Pro Git online book](https://git-scm.com/book/en/v2)
* 06/12 Mon: You can use multiple -m 'commit message' to form a multi-paragraph commit message
* 06/14 Wed: use `git diff --check` to make sure there is no white space error introduced before stage
    `git log master..contrib` == `git log contrib --not master`, show commit in contrib but not in master
* 06/19 Mon: Found out the A...B operator will show all unique commits in A and B

Running tab for learned key commands:

+ `git hist` log nice fake-tree oneline history of current branch
+ `git hist --all` same for all branches
+ `git br -b newbranch` create a newbranch and switch to it
+ `git br --all` show all branches (local and remote)
+ `git br -vv` more detailed info regarding each branch
+ `git switch -` switch/checkout to the previous branch
+ `git remote show origin` gives detailed info regarding the 'origin' remote


HZ

Below is a test result of the .. and ... range operator in Git
Basically,
- A..B means commits in B but not in A
- B..A means comiits in A but not in B
- A...B means both of above: the commits that are unique in A and B

Output result:
```
hongbo@Y510P:~/w/learn_git_2/z1$ git log test1..master --pretty=format:"%h%x09%ad%x09%s" --date=short | nl
     1  1cb03c7 2023-06-19      daily update
     2  d196684 2023-06-16      daily update
     3  130ee1c 2023-06-14      Added daily learnt items
     4  8a45d02 2023-06-12      style: remove trailing space
     5  cc4cb58 2023-06-09      daily diary update
     6  109fc2d 2023-06-08      finish the last mod last night, so can start 0608 Thu
     7  e4bbf70 2023-06-07      added list of commands
hongbo@Y510P:~/w/learn_git_2/z1$ git log master..test1 --pretty=format:"%h%x09%ad%x09%s" --date=short | nl
     1  130f6aa 2023-06-07      corrected md formating, using online wysiwyg tool
     2  692c6dd 2023-06-07      Add detailed explanation of today\'s work
     3  2be82c3 2023-06-07      Merge branch 'master' into test1
     4  81d0176 2023-06-07      local commit 2
     5  de0b1fe 2023-06-07      first local commit
hongbo@Y510P:~/w/learn_git_2/z1$ git log master...test1 --pretty=format:"%h%x09%ad%x09%s" --date=short | nl
     1  1cb03c7 2023-06-19      daily update
     2  d196684 2023-06-16      daily update
     3  130ee1c 2023-06-14      Added daily learnt items
     4  8a45d02 2023-06-12      style: remove trailing space
     5  cc4cb58 2023-06-09      daily diary update
     6  109fc2d 2023-06-08      finish the last mod last night, so can start 0608 Thu
     7  e4bbf70 2023-06-07      added list of commands
     8  130f6aa 2023-06-07      corrected md formating, using online wysiwyg tool
     9  692c6dd 2023-06-07      Add detailed explanation of today\'s work
    10  2be82c3 2023-06-07      Merge branch 'master' into test1
    11  81d0176 2023-06-07      local commit 2
    12  de0b1fe 2023-06-07      first local commit
```
