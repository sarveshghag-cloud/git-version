# Git Staging Area and Commit Guide

This repository explains how files move from the **Working Directory** to the **Staging Area** and finally into a **Commit** in Git.

---

## Git Areas Explained
![ ](./IMG/revert.drawio.png)

### 1️. Working Directory (Current Area)

- This is where you create, edit, or delete files.
- Changes here are **not tracked** until you add them.

## 2️. Staging Area

- The staging area holds changes that are ready to be committed.

- You choose what goes into the next commit.

```
git add .
```

Example

```
git add index.html

```

Check staged files:

```
git status

git status -s 
```
## 3️. Commit Area (Repository)

- A commit saves a snapshot of staged changes into the Git repository.

- Each commit has a unique ID (hash).
```
git commit -m "Add initial version of index page"
```
## 4. Staging Area to Working repo
```
git restore --staged <file_name>
```
example 
```
git restore --staged index.html
```

![](./IMG/stage%20area.png)

## 5. commit area to working repo
![](./IMG/Difference%20reset%20and%20revert%20.png)
```
git commit -m ""
git log --oneline
git log 
git revert --staged <commit id>
    or 
git reset -- staged .
```
example 
```
git commit -m "modifed file "
git log --oneline (copy the commit id)
git revert --staged (paste the commit id)
git reset --staged (paste here)
```


---

![](./IMG/commit%20to%20working.png)

## 6. reset soft command 
- **git reset --soft removes commit but keeps changes**

- Keeps changes staged

- Code is NOT lost
- Changes still in staging area
```
git add .
git commit -m "new changes have done" 
git log --oneline (copy commit id of v2)
git reset --soft (paste here)
```
check the status 
```
git status
```
![](./IMG/reset%20soft.png)

## 7. reset hard command 
- **git reset --hard removes commit and deletes all changes permanently.**

- Clears staging area

- Deletes working directory changes

- Data loss
 
 step 1: make changes in file <br>
 step 2: check status 
 ```
 git status 
 ```
 step 3: Reset hard
 ```
 git reset --hard 

 ```
 ![](./IMG/reset%20hard.png)






