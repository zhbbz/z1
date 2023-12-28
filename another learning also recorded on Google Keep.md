# git command (only in Linux, as it involves bash shell commands)

git-hblistall
1. put file in path
2. content of file:
    git cat-file --unordered --buffer --batch-check --batch-all-object | cut -c'1-6,41-' | sort -k2
3. chmod +x git-hblistall

# alias
  sw = switch

# some learnt ideas/concepts

- The pair of (git diff) vs (git diff --staged)  is similar with the pair (git restore <filename>) vs (git restore --staged <filename>)
    * git diff checks the difference between staged/cached vs in working dir/changed
    * git diff --staged checks between the committed vs the staged
    * git restore <filename> copies back from staged to working dir, i.e., removes unstaged changes
    * git restore --staged <filename> copies back from commit into staged, i.e., de-stage the changes, **has no effect** on working directory 

- git log
  * git log --stat
  * git log --graph
  * git log -- <filename> : find logs only involve the <filename>

- On command line, squash all commit in feature branch, then rebase to master
    * command:
        1. (interactive rebase, or, squash) **`git rebase --keep-base -i master`**
            - the option `--keep-base` means rebase to the last common commit of both feature and master branches. This will squash all feature-branch commits into one. This also save us the trouble to manually find the SHA-1 code of the last common commit
            - the option `-i` is for interactive, this is how we can squash all commit into one
            - Remember when edit the todo file, keep the first commit unchanged, but change all the rest into 's' or 'squash'
            - When another edit window comes, this time it is for the commit message, remember to add one summary line on top. And for all combined individual commit messages, add number, or file name, or related information, so that the final combined message make sense
        2. (real rebase) `git rebase master`
            - Note here, there might be multiple files what are CONFLICT. Remember after edit each file, do git add <file> to **mark** conflict resolved.
        3. (optional) now we can `git switch master`, and `git merge feature` (which is a fast-forward), and master only advance one commit. 

- `git diff --check` for white space error

- `git log contrib --not master`  same as  `git log master..contrib`

- Find common ancestor of two branches

  `git merge-base contrib master` \
  In `git diff`, we can use triple dots to indicate the common ancestor, i.e.\
  `git switch contrib;  git diff master...contrib`, this way we can find what has been introduced by contrib from its branching out of master

- `git reflog`

- Add reflog-like info to log: `git log -g`

- Triple dots have different meaning in `git diff` than in `git log`

  In `git diff`, they mean the common ancestor of both branches,\
  in `git log`, they mean commits that are in either branch, but **not** in both.







