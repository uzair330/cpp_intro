# Beginner’s Step-by-Step: Sign up, create a repo, and push your code to GitHub

**Goal:** In \~15–30 minutes, you’ll create a GitHub account, make a tiny project on your computer, put it under Git (version control), and push it to a brand‑new GitHub repository.

> If any step feels confusing, just follow the commands exactly as shown. You can’t break anything.

---

## 0) What are Git and GitHub (super short)

* **Git** = a tool on your computer that tracks changes to files (version control).
* **GitHub** = a website that stores your Git repositories online so you can share and collaborate.

You’ll use Git locally and GitHub as the remote copy in the cloud.

---

## 1) Sign up (or Sign in) to GitHub

1. Go to **[https://github.com](https://github.com)**.
2. **Sign up** with an email, create a username and password.
3. **Verify your email** (check your inbox and click the verification link).
4. (Recommended) Turn on **Two‑Factor Authentication (2FA)** for security (Settings → Password and authentication → Enable two‑factor).
5. If you already have an account, just **Sign in** instead.

> Remember your **username**. We’ll need it later.

---

## 2) Install Git (one time only)

### Windows

* Download and run the Git installer from **[https://git-scm.com/download/win](https://git-scm.com/download/win)** (accept defaults).

### macOS

* If you have **Homebrew**:

  ```bash
  brew install git
  ```
* Or install Xcode Command Line Tools when prompted the first time you run `git`.

### Linux (Debian/Ubuntu)

```bash
sudo apt update
sudo apt install git
```

**Check it worked:**

```bash
git --version
```

You should see something like `git version 2.x.x`.

### Set your name & email for commits (one time only)

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

---

## 3) Create a project folder (your local repo)

Pick any folder. Here’s an example that works on Windows, macOS, or Linux:

```bash
# Create a folder and go into it
mkdir hello-git
cd hello-git

# Start a brand new Git repository inside this folder
git init
```

You’ll see: `Initialized empty Git repository ...`

---

## 4) Add a very simple file

Create a file named `hello.txt` (or `README.md`).

```bash
echo "Hello Git and GitHub!" > hello.txt
```

Check what Git sees:

```bash
git status
```

You’ll see `hello.txt` as **untracked**.

---

## 5) Make your first commit

Think of a **commit** as a small snapshot.

```bash
# Tell Git to include the new file in the next snapshot
git add hello.txt

# Save the snapshot with a message
git commit -m "Add hello.txt"
```

---

## 6) Create an **empty** repository on GitHub

> We’ll create an **empty** repo to avoid conflicts. Don’t add a README, .gitignore, or license in this step.

1. On GitHub (in your browser), click **+** (top‑right) → **New repository**.
2. **Repository name:** `hello-git` (or any name you like).
3. **Visibility:** Public or Private (your choice).
4. **Do NOT** check “Add a README”, “Add .gitignore”, or “Choose a license”.
5. Click **Create repository**.
6. You’ll land on a page that shows the repo URL. Copy the **HTTPS** URL. It looks like:

   ```
   https://github.com/<your-username>/<your-repo>.git
   ```

---

## 7) Connect your local repo to GitHub and push

We’ll use **HTTPS** because it’s simplest for beginners. Modern Git will open a browser window for you to sign in.

```bash
# Still inside your project folder

# 7.1) Tell Git the address of the remote repo on GitHub
# Replace the placeholders with your GitHub username and repo name

git remote add origin https://github.com/<your-username>/<your-repo>.git

# 7.2) Make sure your main branch is named 'main'
# (If it says you're on 'master', rename the branch to 'main')

git branch -M main

# 7.3) Upload (push) your commits to GitHub

git push -u origin main
```

* The first time, Git may ask you to **sign in** to GitHub. Follow the on‑screen popup and approve access. After that, Git will remember.
* When it finishes, refresh your GitHub repository page—you should see `hello.txt`!

---

## 8) Make a change and push again (practice)

```bash
# Edit the file (append a new line)
echo "A second line." >> hello.txt

# Check what changed
git status

# Stage and commit the change
git add hello.txt
git commit -m "Append a second line to hello.txt"

# Send it to GitHub
git push
```

---

## 9) Starting from GitHub → clone to your computer (bonus)

If you already have a repo on GitHub and want it locally:

```bash
# Go to the folder where you want the project copied
cd /path/where/you/want/it

# Use the HTTPS URL from the repo page

git clone https://github.com/<user>/<repo>.git
cd <repo>
```

Now create files, `git add`, `git commit`, and `git push` as shown earlier.

---

## 10) Common errors & quick fixes

* **`fatal: remote origin already exists`**

  ```bash
  git remote set-url origin https://github.com/<your-username>/<your-repo>.git
  ```
* **Accidentally created README/.gitignore on GitHub (not empty)** and push fails:

  * **Option A (easy):** Pull GitHub’s change first, then push

    ```bash
    git pull --rebase origin main
    git push
    ```
  * **Option B (replace GitHub with your local history)**

    ```bash
    git push --force-with-lease
    ```
* **Authentication failed / wrong credentials**

  * Make sure you’re logged into the popup browser that Git opens, with the **same** GitHub account.
  * If asked for a password on the command line, GitHub requires a **token** (not your real password). Prefer the browser‑based sign‑in when prompted.
* **`repository not found`**

  * Check the URL: username and repo name must be exact, and the repo must exist.
* **On `master` instead of `main`**

  ```bash
  git branch -M main
  git push -u origin main
  ```
* **Nothing to commit**

  * You probably didn’t change or add files yet. Edit a file, then `git add` and `git commit`.

---

## 11) GUI alternative: GitHub Desktop (no terminal)

If the terminal feels scary, use **GitHub Desktop** (free):

1. Install from [https://desktop.github.com](https://desktop.github.com) and sign in with your GitHub account.
2. **File → New Repository** → name: `hello-git` → Create.
3. Create or drag a file into the repo (e.g., `hello.txt`).
4. In the **Changes** tab, write a **summary** and click **Commit to main**.
5. Click **Publish repository** to send it to GitHub.
6. Edit a file → **Commit to main** → **Push origin**.

---

## 12) Tiny cheat‑sheet

```bash
# Start a repo in the current folder
git init
# See what changed
git status
# Stage file(s) for commit
git add <file-or-folder>
# Save a snapshot
git commit -m "your message"
# Connect to GitHub
git remote add origin https://github.com/<you>/<repo>.git
# Push code up to GitHub
git push -u origin main
# Pull latest changes down
git pull
# See the commit history
git log --oneline --graph --decorate --all
```

---

## 13) Next steps (when you’re ready)

* Add a **README.md** that explains your project.
* Create a **.gitignore** to avoid committing secrets or build files.
* Learn **branches** (`git switch -c feature-x`) and **pull requests**.
* Explore **Issues** and **Projects** on GitHub for task tracking.

---

## Appendix A: Example session (copy/paste)

> Replace `<your-username>` and `<your-repo>` before running.

```bash
# Create folder & repo
mkdir hello-git && cd hello-git
git init

echo "Hello Git and GitHub!" > hello.txt
git add hello.txt
git commit -m "Add hello.txt"

git remote add origin https://github.com/<your-username>/<your-repo>.git
git branch -M main
git push -u origin main

# Make a change and push again
echo "A second line." >> hello.txt
git add hello.txt
git commit -m "Append a second line"
git push
```

## Appendix B: Use SSH instead of HTTPS (optional)

SSH avoids browser sign‑ins and is great if you push/pull often.

1. **Generate a key** (press Enter for defaults, set a passphrase if you like):

   ```bash
   ssh-keygen -t ed25519 -C "your.email@example.com"
   ```
2. **Start the agent & add your key**

   ```bash
   # macOS / Linux
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519

   # Windows (PowerShell)
   Start-Service ssh-agent
   ssh-add $env:USERPROFILE\.ssh\id_ed25519
   ```
3. **Copy your public key** and add it to GitHub (Settings → SSH and GPG keys → New SSH key):

   ```bash
   # macOS / Linux
   cat ~/.ssh/id_ed25519.pub
   # Windows (PowerShell)
   type $env:USERPROFILE\.ssh\id_ed25519.pub
   ```
4. **Use the SSH URL** for your repo:

   ```
   git@github.com:<your-username>/<your-repo>.git
   ```

   Set it:

   ```bash
   git remote set-url origin git@github.com:<your-username>/<your-repo>.git
   ```

Now `git push` and `git pull` will use SSH.

---

### You did it!

You’ve created an account, made a repo, committed code, and pushed it to GitHub. Save this page and reuse the commands for your next project.
