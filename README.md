# Project Title

A bare-bones static site: plain HTML + CSS, no build step, no dependencies.

## Structure

```
.
├── index.html      # the page
├── css/style.css   # all styles (CSS variables at the top)
├── js/main.js      # optional; delete if unused
├── .nojekyll       # tells GitHub Pages to serve files as-is
└── .gitignore
```

## Run locally

Just open `index.html` in a browser. Or, for a local server:

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a new repo on GitHub and push this folder to it:

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<user>/<repo>.git
   git push -u origin main
   ```

2. On GitHub: **Settings → Pages → Build and deployment**
   - Source: **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)**
   - Save.

3. Wait ~1 minute. The site goes live at
   `https://<user>.github.io/<repo>/`

### Notes

- Keep all asset paths **relative** (`css/style.css`, not `/css/style.css`). A
  project site is served from a subpath, so leading slashes break.
- `.nojekyll` is what lets files/folders starting with `_` be served.
- To use a custom domain, add a `CNAME` file containing just the domain.
