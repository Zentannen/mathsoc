# Math Society Website

A Quarto website for the Math Society at UBC.

## Local Development

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/)

### Build & Preview

```bash
quarto preview
```

This will start a local server at `http://localhost:4200`

### Build for Production

```bash
quarto render
```

This generates the static site in the `_site/` folder.

## Deploy to GitHub Pages

### Step 1: Initialize Git Repository

```bash
git init
git add .
git commit -m "Initial commit: Quarto website"
```

### Step 2: Create GitHub Repository

1. Go to [GitHub](https://github.com/new)
2. Create a new repository named `mathsoc-website` (or your preferred name)
3. Don't initialize with README, .gitignore, or license

### Step 3: Push to GitHub

```bash
git remote add origin https://github.com/YOUR-USERNAME/mathsoc-website.git
git branch -M main
git push -u origin main
```

### Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Settings → Pages
3. Build and deployment:
   - Source: Deploy from a branch
   - Branch: `main` → `/(root)`
4. Save

### Step 5: Configure GitHub Actions (Optional - for automatic deployment)

Create `.github/workflows/publish.yml`:

```yaml
on:
  push:
    branches: main

name: Publish Website

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: actions/checkout@v3
      - uses: quarto-dev/quarto-actions/setup@v2
      - uses: quarto-dev/quarto-actions/publish@v2
        with:
          target: gh-pages
```

After creating this file, GitHub Actions will automatically build and deploy on every push!

## Customization

- Edit `_quarto.yml` to change site title, navigation, and theme
- Edit individual `.qmd` files to change content
- Modify `styles.css` for custom styling

## Resources

- [Quarto Website Documentation](https://quarto.org/docs/websites/)
- [Quarto GitHub Pages Guide](https://quarto.org/docs/publishing/github-pages.html)
