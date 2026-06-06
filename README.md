# Spann Engineering Consulting LLC — Website

Static website for Spann Engineering Consulting LLC, designed to be hosted on
GitHub Pages. No build step, no JavaScript frameworks, no cookies, no
trackers — just plain HTML, CSS, and SVG.

## Contents

```
.
├── index.html             # Landing page
├── ai-simulation.html     # AI agents driving simulation software
├── medical.html           # Medical devices & pharmaceuticals
├── energy.html            # Clean energy
├── nanotechnology.html    # Nanotechnology / nanomanufacturing
├── mcm.html               # COMAP MCM background
├── about.html             # Team — bio & CV (URL kept as /about.html)
├── contact.html           # Contact (mailto:info@spann.ai)
├── css/
│   └── style.css          # All site styling (dark mode, gradient mesh)
├── assets/
│   ├── logo.svg           # Original brand SVG (#116677 / #800A14)
│   ├── logo-dark.svg      # Brightened variant used on the dark site
│   ├── favicon.svg
│   ├── pattern-flow.svg   # Decorative flowing-curves graphic (hero/headers)
│   └── pattern-mesh.svg   # Subtle triangular-mesh texture (cards/panels)
└── README.md
```

## Local preview

The site is fully static. To preview it locally, either:

- **Open `index.html` directly** in a browser, or
- Serve the directory with any local web server. From the repo root:
  ```powershell
  # Python 3 (built into most systems)
  python -m http.server 8000
  # then visit http://localhost:8000
  ```

## Publishing on GitHub Pages

### Option A — User/organization site (`spann.ai` or `<username>.github.io`)

1. Create a new GitHub repository named `<your-username>.github.io`
   (or `<org-name>.github.io` for an organization).
2. Upload the contents of this folder (not the folder itself) to the root of
   the repository. You can do this through the GitHub web UI
   (**Add file → Upload files**) or via git:
   ```powershell
   git init
   git add .
   git commit -m "Initial commit of Spann Engineering website"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-username>.github.io.git
   git push -u origin main
   ```
3. In the repository, go to **Settings → Pages**.
4. Under **Build and deployment**, set:
   - **Source**: *Deploy from a branch*
   - **Branch**: `main` / `/ (root)`
5. Save. After a minute or two the site will be live at
   `https://<your-username>.github.io/`.

### Option B — Project site (any repo name)

1. Create a repository with any name (e.g. `spann-engineering-website`).
2. Upload the contents of this folder to the repository.
3. Go to **Settings → Pages** and set the source to your `main` branch (root).
4. The site will be live at
   `https://<your-username>.github.io/<repo-name>/`.

### Custom domain (e.g. `spann.ai` or `www.spann.ai`)

1. In **Settings → Pages**, under **Custom domain**, enter your domain
   (e.g. `spann.ai`) and **Save**. GitHub will create a `CNAME` file in the
   repository.
2. At your DNS provider, set the records GitHub recommends:
   - **Apex domain** (`spann.ai`): create four `A` records pointing to
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`,
     `185.199.111.153` (current GitHub Pages IPs — confirm in GitHub's docs).
   - **www subdomain** (`www.spann.ai`): create a `CNAME` record pointing to
     `<your-username>.github.io`.
3. Back in **Settings → Pages**, wait for DNS to propagate, then check the
   **Enforce HTTPS** box.

## Editing content

Each page is a single HTML file with inline content; there is no templating
engine. Common things you may want to edit:

- **Bio and CV** — `about.html` (Team page). Currently marked as a
  placeholder draft.
- **Medical publications & patents** — `medical.html`. Add specific case
  studies as they're cleared.
- **Energy specifics** — `energy.html`. Add or redact details based on
  NDA scope.
- **Nanotech specifics** — `nanotechnology.html`. Add or redact details
  based on NDA scope.
- **MCM resources** — `mcm.html`. A "coming soon" placeholder is in
  place; replace with actual contestant resources after the 2026–2027
  school year begins.
- **Email address** — currently `info@spann.ai`, referenced in every page's
  footer and on `contact.html`.
- **Color palette & background patterns** — colors are defined as CSS
  custom properties at the top of `css/style.css` (the `:root` block).
  Brand colors are `#800A14` and `#116677`; the dark-mode accent is
  `#E8B86D`. The decorative flow and mesh patterns live in
  `assets/pattern-flow.svg` and `assets/pattern-mesh.svg`; both are plain
  SVG and can be edited in any vector tool or text editor.

## Privacy / cookies

The site uses no cookies, no analytics, no third-party fonts, and no
external JavaScript. All assets are served from the same origin. If you
later add analytics or any third-party embed, that will likely introduce
cookies — review carefully if cookie-free behavior is a requirement.
