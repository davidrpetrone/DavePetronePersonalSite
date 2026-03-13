# Dave Petrone — Personal Website

## Deploying to GitHub Pages (with custom Squarespace domain)

### Step 1: Create a GitHub repo
1. Go to [github.com](https://github.com) and create a new public repository named `dave-petrone` (or any name you like)
2. Push this project to that repo:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

### Step 2: Enable GitHub Pages
1. In your GitHub repo, go to **Settings → Pages**
2. Under **Source**, select `main` branch and `/ (root)`
3. Click **Save** — GitHub will give you a URL like `https://yourusername.github.io/your-repo`

### Step 3: Point your Squarespace domain to GitHub Pages
1. In **Squarespace → Domains**, click your domain → **DNS Settings**
2. Add these DNS records:

| Type  | Host | Value                 |
|-------|------|-----------------------|
| A     | @    | 185.199.108.153       |
| A     | @    | 185.199.109.153       |
| A     | @    | 185.199.110.153       |
| A     | @    | 185.199.111.153       |
| CNAME | www  | YOUR_USERNAME.github.io |

3. Back in GitHub Pages settings, add your custom domain (e.g. `www.davepetrone.com`)
4. Check **Enforce HTTPS**

DNS changes can take up to 24 hours to propagate.

### Auto-deploy on every push
Once set up, any `git push` to the `main` branch will automatically update the live site within minutes.
