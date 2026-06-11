# SETUP.md — Creating the Repository and Deploying the Dashboard

Step-by-step instructions for publishing this dashboard as a live GitHub Pages site.
Estimated time: **10–15 minutes**.

---

## Prerequisites

- A GitHub account (free at github.com)
- Git installed on your computer — check by opening Terminal (Mac/Linux) or Command Prompt (Windows) and typing `git --version`
- If Git is not installed: https://git-scm.com/downloads

---

## Step 1 — Create the New Repository on GitHub

1. Go to **https://github.com/new**
2. Fill in the fields:
   - **Repository name:** `say-my-name-llm-bias` (or your preferred name from the options below)
   - **Description:** `Interactive validation dashboard — LLM refusal bias study (Haq & Saldías, FAccT 2026)`
   - **Visibility:** ✅ Public ← required for free GitHub Pages
   - **Initialize this repository with:** leave all boxes unchecked
3. Click **Create repository**
4. GitHub will show you an empty repo page — leave this tab open, you will need the URL

**Repository name options:**
| Name | Best for |
|---|---|
| `say-my-name-llm-bias` | Matches the paper title; memorable for sharing |
| `llm-refusal-bias-validation` | Descriptive; more searchable by topic |
| `haq-saldias-2026-validation` | Makes the secondary validation framing explicit |

---

## Step 2 — Set Up the Files on Your Computer

Create a folder anywhere on your computer (Desktop is fine):

```
say-my-name-llm-bias/
├── llm_bias_dashboard.html
├── README.md
└── SETUP.md                  ← this file (optional to include)
```

Place the files you downloaded from Claude into that folder.

> **Note on the CSV file:** `BOLD_stratified_sample_cleaned.csv` is optional — include it if you want the raw prompt data in the repo for reproducibility. It is not required for the dashboard to run.

---

## Step 3 — Initialize Git and Push to GitHub

Open Terminal (Mac/Linux) or Command Prompt (Windows). Navigate to your folder:

```bash
cd ~/Desktop/say-my-name-llm-bias
```

Run these commands one at a time, in order:

```bash
# 1. Initialize a git repository in the folder
git init

# 2. Stage all files
git add .

# 3. Make the first commit
git commit -m "Initial commit — LLM bias validation dashboard"

# 4. Rename the default branch to 'main'
git branch -M main

# 5. Connect to your GitHub repository
#    Replace YOUR_USERNAME with your actual GitHub username
git remote add origin https://github.com/YOUR_USERNAME/say-my-name-llm-bias.git

# 6. Push the files to GitHub
git push -u origin main
```

When prompted, enter your GitHub username and password.  
> **If GitHub asks for a token instead of a password:** Go to GitHub → Settings → Developer Settings → Personal Access Tokens → Generate new token (classic) → check the `repo` scope → copy the token and paste it as your password.

Refresh your GitHub repo page — your files should now appear.

---

## Step 4 — Enable GitHub Pages

1. In your repository on GitHub, click **Settings** (top menu bar)
2. In the left sidebar, click **Pages**
3. Under **Source**, select:
   - Branch: **main**
   - Folder: **/ (root)**
4. Click **Save**
5. GitHub will show a green banner:  
   *"Your site is live at https://YOUR_USERNAME.github.io/say-my-name-llm-bias/"*

> It can take **2–5 minutes** for the site to go live the first time. Refresh the Pages settings tab until the URL appears.

---

## Step 5 — Update the README with Your Live URL

Once your Pages URL is confirmed, open `README.md` and replace the placeholder:

```markdown
<!-- Find this line: -->
🔗 **[View the interactive dashboard](https://yourusername.github.io/say-my-name-llm-bias)**

<!-- Replace with your actual URL, e.g.: -->
🔗 **[View the interactive dashboard](https://mdbooker.github.io/say-my-name-llm-bias)**
```

Also update the Citation block at the bottom of the README:

```markdown
https://github.com/yourusername/say-my-name-llm-bias
↓
https://github.com/YOUR_ACTUAL_USERNAME/say-my-name-llm-bias
```

Then push the update:

```bash
git add README.md
git commit -m "Update README with live Pages URL"
git push
```

---

## Step 6 — Verify Everything Works

1. Open your GitHub Pages URL in a browser
2. The dashboard should load with all five panels (Overview, Refusal Rates, Odds Ratio Gap, Subadditivity, BOLD Dataset)
3. Test: hover over bars for tooltips, click a bar on the Refusal Rates panel for the arithmetic box, drag the z-test slider

If the page is blank or shows an error, the most common cause is that GitHub Pages is still deploying — wait 3–5 more minutes and hard-refresh (`Ctrl+Shift+R` or `Cmd+Shift+R`).

---

## Making Updates Later

Any time you update the dashboard file:

```bash
# From inside your project folder
git add llm_bias_dashboard.html
git commit -m "Brief description of what changed"
git push
```

GitHub Pages will automatically redeploy within 1–2 minutes.

---

## Optional — Add a Topic Tag on GitHub

On your repository's main page, click the gear icon next to **About** (top right of the file list).

Add these topics so your repo is discoverable:
```
llm-bias  algorithmic-fairness  fairness-accountability  aave  facct  racial-bias  nlp
```

This is low effort and makes the repo findable by researchers using GitHub's topic search.

---

## Sharing the Repo

Once live, you have three links worth keeping:

| What | Link format |
|---|---|
| Repository (code + README) | `https://github.com/YOUR_USERNAME/say-my-name-llm-bias` |
| Live dashboard | `https://YOUR_USERNAME.github.io/say-my-name-llm-bias` |
| Direct HTML file | `https://YOUR_USERNAME.github.io/say-my-name-llm-bias/llm_bias_dashboard.html` |

All three are citable. The live dashboard link is the one to include in the paper's supplementary materials or author note.

---

*Questions about Git commands: https://docs.github.com/en/get-started*  
*Questions about GitHub Pages: https://docs.github.com/en/pages*
