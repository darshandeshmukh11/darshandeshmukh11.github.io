# Hugo Site Setup (local machine)

## 1. Create your Hugo site
```bash
hugo new site my-portfolio
cd my-portfolio
```

## 2. Add the PaperMod theme as a submodule
```bash
git init
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
git submodule update --init --recursive
```

## 3. Copy these starter files into your project
Copy everything from this package into your Hugo project root, overwriting the
default `hugo.yaml`/`config.yaml` and `content/` folder:

```
my-portfolio/
├── config.yaml
├── content/
│   ├── _index.md
│   ├── about.md
│   ├── search.md
│   ├── projects/
│   │   ├── _index.md
│   │   └── sample-project.md
│   └── posts/
│       └── _index.md
├── static/
│   └── images/projects/     (put your screenshots/covers here)
└── .github/workflows/
    └── deploy-hugo.yaml
```

## 4. Update placeholders
Edit `config.yaml` and replace:
- `yourusername` (GitHub, LinkedIn URLs)
- `you@example.com`
- `baseURL` (should match `https://<yourusername>.github.io/` or your custom domain)

## 5. Run locally
```bash
hugo server -D
```
Visit http://localhost:1313

## 6. Enable GitHub Pages
Push this repo to GitHub, then in the repo settings go to
**Settings → Pages → Build and deployment → Source** and select **GitHub Actions**.
The included workflow (`.github/workflows/deploy-hugo.yaml`) will build and
deploy automatically on every push to `main`.

## 7. Add a new project
Create a new file under `content/projects/`, e.g.:
```bash
hugo new projects/my-new-project.md
```
Use `sample-project.md` as a template for front matter (tags, cover image, weight).
