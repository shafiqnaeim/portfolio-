# Go live: portfolio on GitHub Pages (step-by-step)

This guide assumes your site files are in **`portfolio/`** on your PC (with `index.html` inside that folder). You will create a **new empty repository on GitHub**, then **upload your first version with Git** from that folder.

**What you get:** a public URL like  
`https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`  
(works over HTTPS; no server rent; free for public repos.)

---

## 0. Prerequisites (checklist)

| Requirement | You have |
|-------------|----------|
| GitHub account | [Sign up](https://github.com/signup) if needed |
| Git on Windows | You have Git **2.53** installed |
| Portfolio folder | `MyResume\portfolio\` contains `index.html`, `assets\`, etc. |

You do **not** need `gh` (GitHub CLI) for this guide.

---

## 1. Create an empty repository on GitHub (website)

1. Log in at [https://github.com](https://github.com).
2. Click **+** (top right) → **New repository**.
3. **Repository name:** something short, e.g. `portfolio` or `shafiq-portfolio` (letters, numbers, hyphens).
4. **Description (optional):** e.g. “Personal portfolio — UMT Software Engineering”.
5. Choose **Public** (GitHub Pages is free and simplest for public repos).
6. **Do not** add a README, .gitignore, or license (keeps the repo empty so your first push is clean).
7. Click **Create repository**.

GitHub will show a page with setup commands. **Leave that tab open** — you will need the **HTTPS** URL, which looks like:

`https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git`

Replace `YOUR_USERNAME` and `YOUR_REPO_NAME` in your head when you run commands below.

---

## 2. Open Git in the **portfolio** folder (not the whole Desktop)

Your site must live at the **root of the repo** (so `index.html` is at the top level of what you push). The easiest way: make Git’s “home” the **`portfolio`** folder.

1. Open **File Explorer** → go to  
   `C:\Users\User\Desktop\MyResume\portfolio`
2. Click the address bar, type **`cmd`**, press **Enter**  
   (a Command Prompt opens **already in that folder**).

Or open **PowerShell** and run:

```powershell
cd "C:\Users\User\Desktop\MyResume\portfolio"
```

---

## 3. Initialize Git and make the first commit

Run these **one block at a time** (same order).

**Tell Git who you are** (only needed once per machine; use your real name and GitHub email):

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

**Create the repository and first commit:**

```bash
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
```

If `git commit` says **nothing to commit**, your folder is empty or wrong directory — `cd` into `portfolio` again.

---

## 4. Connect to GitHub and push

**Add the remote** (paste **your** URL from step 1):

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
```

**Push:**

```bash
git push -u origin main
```

### First-time login (Windows)

- A **browser window** or **Git Credential Manager** prompt may ask you to sign in to GitHub.
- If it asks for a **password**, use a **Personal Access Token (PAT)**, not your GitHub account password:
  - GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)** → **Generate new token**
  - Enable scope **`repo`**
  - Copy the token once and paste it when Git asks for a password.

After a successful push, refresh the repository page on GitHub — you should see `index.html`, `assets`, `README.md`.

---

## 5. Turn on GitHub Pages

1. On GitHub, open your **repository** (not your profile).
2. **Settings** (top bar of the repo) → left sidebar **Pages**.
3. Under **Build and deployment** → **Source**: choose **Deploy from a branch**.
4. **Branch:** select **`main`** and folder **`/ (root)`** → **Save**.

Wait **1–3 minutes**. GitHub will show a green banner like:

**Your site is live at `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`**

That is your **public portfolio URL**. Open it in a browser.

---

## 6. After you change the site (updates)

From the same `portfolio` folder:

```bash
git add .
git commit -m "Describe your change"
git push
```

Refresh the live site after ~1 minute.

---

## 7. Fix common problems

### Page loads but **no styling** (plain HTML)

- Hard refresh: **Ctrl+F5**.
- Confirm on GitHub that `assets/css/styles.css` exists at **`assets/css/styles.css`** relative to `index.html` (same structure as on your PC).

### **404** on the GitHub Pages URL

- Settings → Pages: confirm branch **`main`** and **`/ (root)`**.
- Wait a few minutes after the first enable.

### **`git push` rejected**

- If you created a README on GitHub when creating the repo, the histories differ. Easiest fix: on GitHub, delete the repo and create a **new empty** repo again, then repeat from step 3 **or** ask someone to help you `git pull --rebase origin main` once.

### You want **`yourname.github.io`** with **no** `/repo-name` in the URL

- Create a repo named exactly **`YOUR_USERNAME.github.io`** (replace with your GitHub username).
- Push the **same** `portfolio` files to the **`main`** branch root.
- Site URL becomes **`https://YOUR_USERNAME.github.io/`** (can take a few minutes the first time).

---

## 8. Optional: faster “go live” without Git (Netlify Drop)

1. Zip the **`portfolio`** folder contents (`index.html` + `assets` + `README`).
2. Go to [https://app.netlify.com/drop](https://app.netlify.com/drop) (free tier).
3. Drag the zip or folder — you get a random `something.netlify.app` URL.

Good for a **quick demo**; GitHub Pages is better long-term if you already use GitHub for code.

---

## 9. Put the link everywhere

- **LinkedIn:** Featured section or “Website” field → your GitHub Pages URL.
- **Resume / portfolio:** same URL.

When your LinkedIn and GitHub URLs exist, set them in **`assets/js/main.js`** as described in `README.md`, commit, and push again.

---

*You asked to be taught, not for the assistant to run `git push` for you — signing in to GitHub must happen on your machine. If you paste your **repo name** (not secrets) and get stuck on one error message, you can share the exact error text and we can interpret it.*
