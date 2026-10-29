first upload
Here is a step-by-step guide to performing the basic Git operations you requested using the command line.

---

### Step 1: Configure Username and Email

Before you start working, tell Git who you are. This ensures your commits are properly attributed to you.

Open your terminal or command prompt and run:

* **Set your username:**
```bash
git config --global user.name "Your Name"

```


* **Set your email:**
```bash
git config --global user.email "your.email@example.com"

```



*(Note: Remove `--global` if you want to apply these settings only to the current repository instead of your entire system).*

---

### Step 2: Initialize a Repository

Navigate to the folder where you want your project to live (or create a new one), and initialize it as a Git repository:

```bash
# Navigate to your folder (or create/cd into one)
cd path/to/your/project

# Initialize Git
git init

```

This creates a hidden `.folder` named `.git` which tracks your project's history.

---

### Step 3: Create a File

Create a new file in your project directory. For example, you can create a simple `README.md` file using your terminal or a text editor:

```bash
echo "# My First Git Project" > README.md

```

---

### Step 4: Stage Changes

Git doesn't track changes automatically until you explicitly tell it to. To prepare your new file to be saved, **stage** it:

```bash
git add README.md

```

*(Tip: You can stage all modified and new files at once by running `git add .`)*

---

### Step 5: Commit the File

Now that your file is staged, save a snapshot of it to your repository's history with a descriptive commit message:

```bash
git commit -m "Initial commit: add README.md file"

```

---

### Quick Verification

To check the status of your repository and ensure everything was committed successfully, run:

```bash
git status

```

If everything is clean and saved, it will output a message like: `nothing to commit, working tree clean`.
Here is a demonstration of how to use **`git status`**, **`git diff`**, and **`git log`** to inspect your repository's state, review changes, and view your commit history.

---

### 1. `git status`

The `git status` command shows the current state of your working directory and staging area. It tells you which files are modified, staged, or untracked.

* **Scenario:** Imagine you just edited your `README.md` file, but you haven't staged it yet, and you also created a new file called `notes.txt`.
* **Command:**
```bash
git status

```


* **What you will see:**
```text
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
  (use "git restore --staged <file>..." to discard changes in working directory)
	notes.txt

no changes added to commit (use "git add " and/or "git commit -a")

```



---

### 2. `git diff`

The `git diff` command shows the exact line-by-line changes (additions and deletions) you have made to your files.

* **How it works:**
* **Unstaged changes:** Running plain `git diff` shows changes in your working directory that **have not** been staged yet.
* **Staged changes:** Running `git diff --staged` shows changes that **have** been added to the staging area and are ready to be committed.


* **Command (for unstaged changes):**
```bash
git diff

```


* **What you will see:**
```text
diff --git a/README.md b/README.md
index 83db4fd..5f12e84 100644
--- a/README.md
@@ -1 +1,3 @@
 # My First Git Project
+
+This is a new line added to the README file.

```


*(Lines starting with `+` represent additions, while lines starting with `-` represent deletions).*

---

### 3. `git log`

The `git log` command displays the chronological history of commits made in the repository, starting with the most recent.

* **Command:**
```bash
git log

```


* **What you will see:**
```text
commit 7f8a9b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8a (HEAD -> main)
Author: Your Name <your.email@example.com>
Date:   Thu Oct 29 14:15:00 2026 +0530

    Initial commit: add README.md file

```


* **Useful Shortcuts for `git log`:**
* **One-line view (compact):**
```bash
git log --oneline

```


*Output:* `7f8a9b2 Initial commit: add README.md file`
* **Graph view (great for branches):**
```bash
git log --oneline --graph --all

```





---

### Summary Workflow Example

To see these commands in action together, you can run this quick sequence:

```bash
# 1. Check what's going on
git status

# 2. See what changes you just made
git diff

# 3. Stage and commit your changes
git add .
git commit -m "Update README and add notes"

# 4. Look back at your history
git log --oneline

```
