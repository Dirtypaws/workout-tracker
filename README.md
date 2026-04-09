# Workout Tracker

An 8-week strength training tracker for my son. Hosted on GitHub Pages, stores data as a flat JSON file in this repo via the GitHub API.

## Setup

### 1. Edit `config.js`
Open `config.js` and set your GitHub username:

```js
const GITHUB_CONFIG = {
  owner: "YOUR_GITHUB_USERNAME",  // ← change this
  repo:  "workouts",
  branch: "main",
  dataFile: "data.json"
};
```

### 2. Create the repo on GitHub
- Go to github.com → New repository
- Name it `workouts`
- Set it to **Public** (required for GitHub Pages)
- **Do not** initialize with a README (we already have one)

### 3. Push this project
```bash
git remote add origin https://github.com/YOUR_USERNAME/workouts.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

### 4. Enable GitHub Pages
- Go to your repo → Settings → Pages
- Source: **Deploy from a branch**
- Branch: `main` / `/ (root)`
- Save — your site will be live at `https://YOUR_USERNAME.github.io/workouts/`

### 5. Create a Personal Access Token
- Go to: https://github.com/settings/tokens/new
- Note: "Workout Tracker"
- Scopes: check **repo**
- Generate and copy the token (you only see it once)

### 6. Connect in the browser
- Open your GitHub Pages URL
- Paste your token into the prompt
- It's saved in your browser's localStorage — you only do this once per browser

## How it works

Every time you type in the tracker, it waits 2 seconds then writes your data to `data.json` in this repo via the GitHub API. The file is committed automatically. When you open the page, it reads the latest `data.json` from GitHub.

Your token is stored only in your browser (localStorage) and is only ever sent to `api.github.com`.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The tracker app |
| `config.js` | Repo configuration (owner, repo name) |
| `data.json` | Your workout data (auto-updated by the app) |
| `.gitignore` | Ignores local-only files |
