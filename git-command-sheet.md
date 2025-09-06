# 📘 Git Command Sheet

A concise reference for **Git** commands.

---

## ⚙️ Configure Git

### 🌍 Global (applies to all repositories)
```bash
# Set global name
git config --global user.name "Your Name"

# Set global email
git config --global user.email "your@email.com"
```

### 📂 Local (specific to a repository)
```bash
# Set local name (for this repo only)
git config --local user.name "Your Name"

# Set local email (for this repo only)
git config --local user.email "your@email.com"
```

---

## 🏗️ Initialize & Clone

### 🆕 Initialize a Git repository
```bash
git init
```

### 📥 Clone a repository
```bash
# Clone into a new directory
git clone [url]

# Clone into the current directory
git clone [url] .

# Clone into a specific directory
git clone [url] [path-to-clone]
```

---

## 📌 Stage & Snapshot

### 🔎 Check file status
```bash
git status
```

### ➕ Add files to the staging area
```bash
# Stage a specific file
git add [file]

# Stage all files
git add .
```

### ➖ Remove files from the staging area
```bash
# Unstage a specific file
git reset [file]

# Unstage all files
git reset .
```

### 📝 Check file changes
```bash
# Show unstaged changes
git diff

# Show staged changes
git diff --staged
```

### 💾 Commit changes
```bash
# Commit with a message
git commit -m "Commit message"

# Commit with title and description
git commit -m "Commit title" -m "Commit description"
```

---

## 🌿 Branching

### 📋 List branches
```bash
git branch
```

### 🌱 Create a new branch
```bash
git branch [branch-name]
```

### 🔀 Switch to another branch
```bash
git checkout [branch-name]
```

### ✏️ Rename the current branch
```bash
git branch -M [new-branch-name]
```

### 🕒 View commit history
```bash
git log
```

---

## 🔄 Share & Update

### 🌐 Remote repositories
```bash
# Add a remote
git remote add [alias] [url]

# List remotes
git remote -v

# Show details of a remote
git remote show [alias]

# Get the URL of a remote
git remote get-url [alias]

# Remove a remote
git remote remove [alias]
```

### 📤 Fetching & pushing
```bash
# Fetch and merge changes from remote
git pull

# Push and set upstream for the first time
git push -u [alias] [branch]

# Push to a specific remote and branch
git push [alias] [branch]

# Push to the default remote/branch
git push
```

---

## 🚫 Ignoring Files

Create a `.gitignore` file to exclude files/folders from being tracked:
```
logs/
*.notes
pattern*/
```

---

# References
- [Complete Git & GitHub Tutorial - by Piyush Garg](https://www.youtube.com/watch?v=TsSjgkfAeJ0)
- [Complete Git and GitHub Tutorial for Beginners - by Piyush Garg](https://www.youtube.com/watch?v=RDxQEzXN8AU)
- [Complete Git & GitHub Tutorial | Branching And Merging - by Piyush Garg](https://www.youtube.com/watch?v=LF-rK5yPzVM)