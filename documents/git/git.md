# **Git Cheat Sheet - Detailed Study Notes**

---

## **1. Introduction to Git**
Git is a free and open-source distributed version control system used for tracking changes in source code during software development. It helps developers collaborate, maintain version history, and manage project updates efficiently.

### **Key Features of Git:**
- **Distributed Version Control:** Every developer has a complete copy of the repository.
- **Branching & Merging:** Enables working on different features simultaneously.
- **Efficient Tracking:** Tracks changes in files and directories.
- **Collaboration:** Allows multiple developers to work on the same project.
- **Security:** Uses SHA-1 hashing to secure the integrity of version history.

---

## **2. Setting Up Git**
### **User Configuration**
Before using Git, user information should be configured:

```sh
git config --global user.name "[name]"
git config --global user.email "[valid-email]"
git config --global color.ui auto
```

- **`user.name`** → Sets an identifiable name for commits.
- **`user.email`** → Associates an email address with commits.
- **`color.ui auto`** → Enables color-coded command-line output.

---

## **3. Initializing and Cloning Repositories**
### **Initializing a Repository**
To start tracking files with Git in an existing directory:
```sh
git init
```
This creates a `.git` directory inside the project, which stores all Git-related information.

### **Cloning a Repository**
To download a repository from a remote source (e.g., GitHub):
```sh
git clone [repository_url]
```
This creates a local copy of the remote repository.

---

## **4. Tracking Changes with Staging & Snapshots**
Git follows a **three-stage workflow**:
1. **Working Directory** → Modified but untracked files.
2. **Staging Area** → Files added to be committed.
3. **Repository** → Permanent commit history.

### **Common Commands**
- **Check status of files**
  ```sh
  git status
  ```
- **Stage files for commit**
  ```sh
  git add [file]
  ```
- **Unstage a file but keep changes**
  ```sh
  git reset [file]
  ```
- **View unstaged changes**
  ```sh
  git diff
  ```
- **View staged changes**
  ```sh
  git diff --staged
  ```
- **Commit staged files with a message**
  ```sh
  git commit -m "[descriptive message]"
  ```

---

## **5. Branching & Merging**
Git allows developers to work on multiple branches independently.

### **Branch Management**
- **List all branches**
  ```sh
  git branch
  ```
  _(The active branch is marked with `*`.)_
  
- **Create a new branch**
  ```sh
  git branch [branch-name]
  ```
  
- **Switch to a branch**
  ```sh
  git checkout [branch-name]
  ```
  
- **Merge branches**
  ```sh
  git merge [branch-name]
  ```
  
- **View commit history**
  ```sh
  git log
  ```

---

## **6. Sharing & Updating Remote Repositories**
Git allows syncing changes with remote repositories.

### **Common Commands**
- **Add a remote repository alias**
  ```sh
  git remote add [alias] [url]
  ```
- **Fetch latest changes from a remote**
  ```sh
  git fetch [alias]
  ```
- **Merge remote branch into the current branch**
  ```sh
  git merge [alias]/[branch]
  ```
- **Push local changes to remote repository**
  ```sh
  git push [alias] [branch]
  ```
- **Pull latest changes from remote repository**
  ```sh
  git pull
  ```

---

## **7. Tracking File Changes**
### **Removing and Renaming Files**
- **Delete a file and stage the change**
  ```sh
  git rm [file]
  ```
- **Move or rename a file**
  ```sh
  git mv [existing-path] [new-path]
  ```
- **Show log with file movement tracking**
  ```sh
  git log --stat -M
  ```

---

## **8. Temporary Commits with Stashing**
If you need to switch branches but have uncommitted changes, you can **stash** them.

### **Common Commands**
- **Save current changes**
  ```sh
  git stash
  ```
- **View list of stashed changes**
  ```sh
  git stash list
  ```
- **Restore last stashed changes**
  ```sh
  git stash pop
  ```
- **Discard last stash**
  ```sh
  git stash drop
  ```

---

## **9. Rewriting History**
Modifying commit history can be risky but useful for cleaning up mistakes.

- **Reapply commits on top of another branch**
  ```sh
  git rebase [branch]
  ```
- **Reset branch to a previous commit**
  ```sh
  git reset --hard [commit]
  ```

---

## **10. Inspecting & Comparing Changes**
Git provides various commands to inspect changes.

### **Viewing Logs & Differences**
- **View commit history**
  ```sh
  git log
  ```
- **Show commits on one branch but not another**
  ```sh
  git log branchB..branchA
  ```
- **View commit history of a specific file (including renames)**
  ```sh
  git log --follow [file]
  ```
- **Compare differences between branches**
  ```sh
  git diff branchB...branchA
  ```
- **Show details of a specific commit**
  ```sh
  git show [SHA]
  ```

---

## **11. Ignoring Files**
To prevent Git from tracking unnecessary files, create a `.gitignore` file.

### **Global Ignore Patterns**
```sh
git config --global core.excludesfile [file]
```

### **Example `.gitignore` File**
```
# Ignore all log files
logs/

# Ignore all .notes files
*.notes

# Ignore all files inside pattern/ directory
pattern/
```

---
