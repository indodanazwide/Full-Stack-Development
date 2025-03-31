# **GitHub - Detailed Study Notes**  

---

## **1. Introduction to GitHub**
GitHub is a cloud-based platform that provides hosting for **Git repositories** and facilitates **collaboration, version control, and project management** for developers.  

### **Key Features of GitHub**
- **Remote Repository Hosting** – Stores Git repositories online.
- **Collaboration & Teamwork** – Allows multiple developers to work on the same project.
- **Issue Tracking** – Enables reporting and fixing bugs efficiently.
- **Pull Requests (PRs)** – Supports reviewing and merging code changes.
- **GitHub Actions** – Automates workflows such as testing and deployment.
- **Security & Code Protection** – Provides branch protection, dependency scanning, and security alerts.
- **Markdown Support** – Enables formatting documentation in `.md` files.

---

## **2. Setting Up GitHub**
### **Creating an Account**
1. Visit [GitHub](https://github.com/) and sign up.
2. Choose a plan (Free, Pro, Team, or Enterprise).
3. Set up **2-factor authentication (2FA)** for security.

### **Connecting GitHub with Git**
After installing Git on your system, connect it with GitHub:  
```sh
git config --global user.name "[your GitHub username]"
git config --global user.email "[your GitHub email]"
```
Then authenticate using **SSH Keys** or **Personal Access Tokens (PATs)**.

#### **Generating an SSH Key**
1. Run:
   ```sh
   ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
   ```
2. Copy the generated key:
   ```sh
   cat ~/.ssh/id_rsa.pub
   ```
3. Add it to GitHub:  
   - Go to **Settings > SSH and GPG keys**  
   - Click **New SSH Key** and paste the key  

---

## **3. GitHub Repository Basics**
### **Creating a Repository**
1. Click **New Repository** on GitHub.
2. Provide a repository name, description, and choose:
   - **Public or Private** visibility.
   - **Initialize with README** (optional).
   - Add a **.gitignore** file (optional).
   - Choose a **license** (optional).

### **Cloning a Repository**
To copy a remote repository to your local machine:
```sh
git clone [repository_url]
```
Example:
```sh
git clone https://github.com/user/repository.git
```

### **Adding a Remote Repository**
If you created a local repository and want to push it to GitHub:
```sh
git remote add origin [repository_url]
git branch -M main
git push -u origin main
```

---

## **4. Committing and Pushing Changes**
After modifying files, follow these steps:

### **Step 1: Check Status**
```sh
git status
```

### **Step 2: Stage Changes**
```sh
git add [filename]   # Stage a single file
git add .            # Stage all modified files
```

### **Step 3: Commit Changes**
```sh
git commit -m "Descriptive commit message"
```

### **Step 4: Push to GitHub**
```sh
git push origin [branch]
```
Example:
```sh
git push origin main
```

---

## **5. Branching & Merging on GitHub**
Branches allow developers to work on features separately.

### **Creating a Branch**
```sh
git branch [branch-name]
```

### **Switching to a Branch**
```sh
git checkout [branch-name]
```
OR
```sh
git switch [branch-name]
```

### **Pushing a New Branch to GitHub**
```sh
git push -u origin [branch-name]
```

### **Merging a Branch**
1. Switch to the main branch:
   ```sh
   git checkout main
   ```
2. Merge another branch:
   ```sh
   git merge [branch-name]
   ```
3. Push changes:
   ```sh
   git push origin main
   ```

### **Deleting a Branch**
```sh
git branch -d [branch-name]      # Delete locally
git push origin --delete [branch-name]  # Delete on GitHub
```

---

## **6. Pull Requests (PRs)**
A **Pull Request (PR)** is used to propose changes and review code before merging.

### **Creating a Pull Request**
1. **Push changes to a branch**:  
   ```sh
   git push origin [branch-name]
   ```
2. On GitHub, navigate to the repository.
3. Click **Pull Requests > New Pull Request**.
4. Choose the branches to compare (e.g., `feature-branch → main`).
5. Add a title and description.
6. Click **Create Pull Request**.
7. After approval, click **Merge**.

---

## **7. Forking & Contributing to Open-Source**
Forking allows users to make copies of others' repositories and contribute.

### **Forking a Repository**
1. Go to a repository on GitHub.
2. Click **Fork** (top right).
3. Clone the forked repository to your local machine:
   ```sh
   git clone https://github.com/your-username/forked-repo.git
   ```
4. Make changes and push them:
   ```sh
   git add .
   git commit -m "Your changes"
   git push origin main
   ```
5. Open a Pull Request to the original repository.

---

## **8. GitHub Issues & Discussions**
Issues are used for bug tracking, feature requests, or discussions.

### **Creating an Issue**
1. Navigate to **Issues** tab in the repository.
2. Click **New Issue**.
3. Add a title, description, and labels (e.g., `bug`, `enhancement`).
4. Click **Submit**.

### **GitHub Discussions**
- A forum-like feature for project-related topics.
- Found in the **Discussions** tab of a repository.

---

## **9. GitHub Actions (Automation & CI/CD)**
GitHub Actions automate workflows such as testing and deployment.

### **Creating a Workflow**
1. Create `.github/workflows/ci.yml` in the repository.
2. Example **CI/CD Workflow**:
   ```yaml
   name: CI Workflow
   on: [push, pull_request]
   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v2
         - name: Run Tests
           run: npm test
   ```
3. Commit and push to trigger the workflow.

---

## **10. GitHub Packages & Releases**
### **GitHub Packages**
- A package registry to publish and manage dependencies.
- Supports **Docker, npm, Maven, Gradle, NuGet**, etc.

### **GitHub Releases**
- Allows publishing software versions with changelogs and binaries.
- Found in the **Releases** tab of a repository.

---

## **11. Security Features in GitHub**
- **Branch Protection** – Restricts direct pushes to main branches.
- **Code Scanning** – Identifies security vulnerabilities.
- **Secret Scanning** – Detects sensitive information in repositories.
- **Dependency Alerts** – Warns about security risks in dependencies.

---

## **12. Exploring Advanced GitHub Features**
- **GitHub Copilot** – AI-powered code suggestions.
- **GitHub Projects** – Task management tool similar to Trello.
- **GitHub Pages** – Free static website hosting for repositories.
- **GitHub CLI (`gh`)** – Command-line tool for managing GitHub.
  ```sh
  gh repo create
  gh pr create --title "My PR" --body "Details"
  ```

---

Explore **GitHub Docs** ([docs.github.com](https://docs.github.com/)) for further learning.