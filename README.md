# Balaji CS - IT Services Website

## Deploy to GitHub Pages

### Step 1: Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new) and create a new repository
2. Choose a name:
   - For a **user site** (e.g., `yourusername.github.io`): name the repo exactly `yourusername.github.io`
   - For a **project site** (e.g., `yourusername.github.io/balajics`): name it anything like `balajics`

### Step 2: Push This Code

```bash
cd project-folder
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/your-repo-name.git
git push -u origin main
```

### Step 3: Configure GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **GitHub Actions**
3. The workflow will run automatically on the next push

### Step 4: Update Base Path (Project Sites Only)

If you created a **project site** (not `username.github.io`), edit `.github/workflows/deploy.yml` and change:

```yaml
BASE_PATH: "/"
```

to:

```yaml
BASE_PATH: "/your-repo-name/"
```

Then push again.

### Step 5: Custom Domain (Optional)

To use a custom domain like `balajics.in`:

1. Go to repo **Settings** → **Pages** → **Custom domain**
2. Enter your domain (e.g., `balajics.in`)
3. Add these DNS records at your domain registrar:

   **For apex domain (balajics.in):**
   | Type | Name | Value |
   |------|------|-------|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |

   **For www subdomain:**
   | Type | Name | Value |
   |------|------|-------|
   | CNAME | www | yourusername.github.io |

4. Check **Enforce HTTPS** once DNS propagates
5. When using a custom domain, keep `BASE_PATH: "/"` in the workflow

## Local Development

```bash
npm install
npm run dev     # starts at http://localhost:3000
npm run build   # builds to ./out
npm run preview # preview production build
```
