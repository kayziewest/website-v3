# Oyster website (static build)

178 pages, one folder per URL (`<path>/index.html`), plus `sitemap.xml`, `robots.txt`, `.nojekyll` and `assets/`.
All internal links and asset paths are RELATIVE, so the site works at a domain root OR under a GitHub Pages
project subpath (username.github.io/repo/). Every page has its own title, meta description, canonical, Open
Graph tags and JSON-LD. External destinations are wired: auth -> dash.oysterskin.com, consumer -> app.oysterskin.com,
API -> oysterskin.readme.io, widget/SDK -> widget.docs.oysterskin.com, evaluation -> labs.oysterskin.ai.

## View it on GitHub Pages (no build step)
1. Create a new repo on github.com, e.g. `oyster-site` (Public).
2. Add these files to the repo. Easiest: repo home > Add file > Upload files, drag the UNZIPPED folder's
   contents (not the zip), commit. Or with git:
       git init && git add -A && git commit -m "Oyster website v2"
       git branch -M main
       git remote add origin https://github.com/<you>/oyster-site.git
       git push -u origin main
3. Repo Settings > Pages > Source: Deploy from a branch > Branch: main, folder: / (root) > Save.
4. Wait about a minute. Site is live at https://<you>.github.io/oyster-site/

`.nojekyll` is included so GitHub Pages serves the files as-is. Canonical tags point to oysterskin.com
(the intended final domain), which is correct for SEO whenever you move it to the real domain.

## Any other static host
Point Vercel/Netlify/Cloudflare Pages/S3 at this folder as the web root. vercel.json and netlify.toml are included.
