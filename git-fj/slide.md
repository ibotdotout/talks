class: center, middle

# Git
## @fungjai
---

# Me?

.right[![](https://avatars0.githubusercontent.com/u/686676?v=3&s=460)]

```sh
$ who
> ibot.out
> http://fb.me/botblogblog
> https://github.com/ibotdotout
```
--

```sh
$ do
> Vim
> Git
> Python
> NodeJS
> Automated Testing
> Automated Workflow
> Dev-ops
> Docker
> Agile / XP
```

---

class: center, middle
# Git - distributed version control

---

# Centralized version control

<br>

```
   Commit
           +------------+
           |            |
A +------+ |   Server   +----------+ C
           |            |
           +-----+------+
                 |
                 |
                 |
                 +
                 B
```

---

# Git - distributed version control

<br>

```
   Commit            Push
         +-------+          +------------+            +-------+
         |       |          |            |            |       |
A   +--+ | RepoA | +------+ |  Original  +----------+ | RepoC |  +---+  C
         |       |          |            |            |       |
         +-------+          +-----+------+            +-------+
                                  |
                                  |
                                  |
                                  |
                                  +

                              +-------+
                              |       |
                              | RepoB |
                              |       |
                              +-------+

                                  +
                                  |
                                  +

                                  B
```
---

class: center, middle
# brief of
## [A Tale of Three Trees by Scott Chacon](https://speakerdeck.com/schacon/a-tale-of-three-trees)

---

class: center, middle

# Three Tree
## HEAD, Index, Working Directory

---

# Tree Flow

```
+----------+           +-----------+           +---------------+
|          |           |           |           |               |
|   HEAD   |           |   Index   |           |  Working Dir  |
|          |           |           |           |               |
+----------+           +-----------+           +---------------+

     +                      +                          +
     |                      |         git add          |
     |                      |   <-------------------+  |
     |                      |                          |
     |                      |         git reset        |
     |                      |   +--------------------> |
     |      git commit      |                          |
     |  <----------------+  |                          |
     |                      |                          |
     |                 git checkout                    |
     |  +-------------------+----------------------->  |
     |                      |                          |
     +                      +                          +
```


Tree Roles:
- HEAD - last commit
- Index - proposed next commit
- Working Directory - sandbox

---

class: center, middle
# Branch

---

# Branch

<br>

local

```
A -- B -- C -- D (HEAD -> master)
      \
       E -- F (develop)
```

<br>

global

```
A -- B -- C -- D (HEAD -> master)
        \
          (origin/master)
```

---

# Commit

<br>

```
A -- B -- C -- D (HEAD -> master)
      \
       E -- F (develop)
```

<br>

```
$ git commit -am "fix typo"
```

<br>

--

```
A -- B -- C -- D -- G (HEAD -> master)
      \
       E -- F (develop)
```

---

# Stash

<br>

```
A -- B -- C -- D - X
                \
                 (HEAD -> master)
```

<br>

```
$ git stash
$ git stash pop
```

<br>

--

```
A -- B -- C -- D  (HEAD -> master)

        stash: [X]
```

---

# Merge

<br>

```
A -- B -- C -- D -- G  (HEAD -> master)
      \
       E -- F -- H  (develop)
```

<br>

```
$ git merge develop
```

<br>

--

```
A -- B -- C -- D -- G -- I (HEAD -> master)
      \                 /
       E -- F -- H ---
                  \
                   (develop)
```

---

# Rebase (!!! rewritten history)

<br>

```
A -- B -- C -- D -- G  ( master)
      \
       E -- F -- H  (HEAD -> develop)
```

<br>

```
$ git rebase master
```

<br>

--

```
A -- B -- C -- D -- G  ( master)
                     \
                      E -- F -- H  (HEAD -> develop)
```

---

# Push

<br>

```
A -- B -- C -- D (HEAD -> master)
        \
          (origin/master)
```

<br>

```
$ git push origin master
```

<br>

--

```
A -- B -- C -- D (HEAD -> master, origin/master)
```

---

# Pull

<br>

```
A -- B  (HEAD -> master)
      \
       C -- D (origin/master)
```

<br>

```
$ git pull origin master
```

<br>

--

```
A -- B -- C -- D (HEAD -> master, origin/master)
```

---

# Pull (merge)

<br>
```
A -- B  -- E (HEAD -> master)
      \
       C -- D (origin/master)
```
<br>

```
$ git pull origin master
```

<br>

--

```
A -- B  -- E -- F  (HEAD -> master)
      \       /
       C -- D (origin/master)
```

---

# Pull (rebase)

<br>

```
A -- B  -- E (HEAD -> master)
      \
       C -- D (origin/master)
```
<br>

```
$ git pull --rebase origin master
```

<br>

--

```
A -- B -- C -- D  -- E  (HEAD -> master)
                 \
                   (origin/master)
```

---

# Checkout (commit)

<br>

```
A -- B -- C -- D  -- E  (HEAD -> master)
```

<br>

```
$ git checkout HEAD~1
```

<br>

--

```
A -- B -- C -- D  -- E  (master)
               \
                (HEAD)
```

---

# Revert

```
A -- B -- C -- D  -- E  (HEAD -> master)
```

<br>

```
$ git revert D
```

<br>

--

```
A -- B -- C -- D  -- E -- D'  (HEAD -> master)
```

---

# Reset Commit (!!! rewritten history)

<br>

```
A -- B -- C -- D  -- E  (HEAD -> master)
```

<br>

```
$ git reset --hard D (discard change)
$ git reset --soft D (keep change)
```

<br>

--

```
A -- B -- C -- D  (HEAD -> master)
```

---

# Cherry-pick

<br>
```
A -- B -- C -- D -- G  ( HEAD -> master)
      \
       E -- F -- H  (fix can't play)
```

<br>

```
$ git cherry-pick E
$ git cherry-pick H
```

--

<br>

```
A -- B -- C -- D -- G -- I[E] -- J[H] ( HEAD -> master)
      \
       E -- F -- H  (fix can't play)
```

--

---

# Squash (!!! rewritten history)

<br>

```
A -- B -- C -- D -- G  ( HEAD -> master)
```

<br>

```
$ git rebase -i B
pick C refactor code
squash D refactor code
pick G add featur
```

<br>

--

```
A -- B -- H[CD] -- I[G]  (HEAD -> master)
```
---

class: center, middle
# How to avoid conflict

---

# [Atomic commit](https://www.freshconsulting.com/atomic-commits/)

Atomic Approach - SEAN PATTERSON
1. Commit each fix or task as a separate change

   ```
   Don't mix feature, fix, refactor in one commit.
   ```

2. Only commit when a block of work is complete

   ```
   Don't add your experimental.
   ```

3. Commit each layout change separately

    ```
    commit A - feat(transform-playlist): add see more
    commit B - feat(html-playlist): add see more of playlist
    commit C - feat(css-playlist): improve see more of playlist
    ```

4. Joint commit for layout file, code behind file, and additional resources

    ```
    commit C - feat(css-playlist): improve see more of playlist
    - playlists.css
    - icon.png
    - constant.ts
    ```
---

# Fetch & Merge, don't Pull

<br>

```
A -- B -- C -- D -- G (HEAD -> master)
```

<br>
```
$ git pull origin master
```
<br>

--

```
A -- B -- C -- D -- F -- H (HEAD -> master, confict!!!)
                \      /
                   G (origin/master)
```

---

# Fetch & Merge, don't Pull (Cont.)

<br>

```
A -- B -- C -- D -- G (HEAD -> master)
```

<br>
```
$ git fetch origin master
```
<br>

--

```
A -- B -- C -- D -- F (HEAD -> master)
                \
                  G (origin/master)
```

--

<br>
```
$ git merge origin/master
```
<br>

```
A -- B -- C -- D -- F -- H (HEAD -> master, confict!!!)
                \      /
                   G (origin/master)
```

---

class: center, middle
# Tell other what are you doing

---

class: center, middle
# How to solve confilct

- edit confilct < tools >
- add confilct
- commit merge/rebse

- abort

---

# Learn

- [Code School - Git](https://www.codeschool.com/learn/git)
- [LearnGitBranching](http://learngitbranching.js.org)

---

# References

- [A Tale of Three Trees](https://speakerdeck.com/schacon/a-tale-of-three-trees)
- [DEVELOPER TIP: KEEP YOUR COMMITS “ATOMIC”](http://www.freshconsulting.com/atomic-commits/)
- [GitCommitMessages](https://wiki.openstack.org/wiki/GitCommitMessages)
- [Linux.conf.au 2013 - Git For Ages 4 And Up](https://www.youtube.com/watch?v=1ffBJ4sVUb4)
- [Git by ibotdotout](http://dev.im-bot.com/tags/#git)

---
