# Mikang Moon — Portfolio

A pixel-art, Frutiger Aero portfolio. It is a plain static website (HTML, CSS and a little JavaScript), so it needs no build step to publish.

## Publish on GitHub Pages
1. Create a new repository on GitHub (for example `mikangmoon.github.io`, or any name).
2. Upload **everything in this folder** (all the `.html` files, `assets/`, `.nojekyll`, `robots.txt`) to the repository root. Drag the folders into the GitHub upload page, or use `git`:
   ```
   git init
   git add .
   git commit -m "Publish portfolio"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
3. In the repository go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, pick **main** and **/ (root)**, then **Save**.
4. After a minute or two your site is live at `https://<your-username>.github.io/<your-repo>/` (or `https://<your-username>.github.io/` if the repo is named `<your-username>.github.io`).

### Use your own domain (optional, e.g. mikangmoon.com)
1. In **Settings → Pages → Custom domain**, enter your domain and save (GitHub adds a `CNAME` file for you).
2. At your domain registrar, add these DNS records, then wait for them to update:
   - Four `A` records for `@` pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One `CNAME` record for `www` pointing to `<your-username>.github.io`
3. Turn on **Enforce HTTPS** once GitHub offers it.

If `mikangmoon.com` currently points at Webflow, change its DNS records at the registrar so it points to GitHub instead. The three older projects that link to `mikangmoon.webflow.io` will keep working as long as that Webflow site stays up.

## What is in this folder
| Path | What it is |
| --- | --- |
| `index.html` | Home page |
| `quests.html` | All projects (opened by "Quests" and "View more projects") |
| `about.html` | About page, with the resume preview and download |
| `contact.html` | Contact page |
| `cozycorner.html`, `mbti-community-app.html`, `cutgroup-proof-of-service.html`, `data-driven-detroit.html` | Project case studies |
| `404.html` | Page shown for a missing address |
| `assets/img/` | All images, grouped by page (`shared/` holds images used on several pages) |
| `assets/css/tailwind.css` | The compiled Tailwind styles (no CDN needed) |
| `assets/resume/` | The resume PDF behind the "Download resume" button |
| `assets/favicon.png` | Browser tab icon |

## Editing tips
- **Replace the resume:** swap `assets/resume/Mikang_Moon_Resume.pdf`. The resume preview image on the About page is `assets/img/about/preview-of-mikang-moon-s-one-page-resume-*.webp`; replace it too so the preview matches.
- **Add or change an image:** put the file in `assets/img/` and update the `src` in the page.
- **Changing styles:** the page-specific look lives in the `<style>` block at the top of each page; layout utilities come from `assets/css/tailwind.css`. If you add new Tailwind class names, rebuild that file with Tailwind CSS v3 (`npx tailwindcss -i input.css -o assets/css/tailwind.css --content "./*.html" --minify`, where `input.css` contains the three `@tailwind base; @tailwind components; @tailwind utilities;` lines).
- Fonts (Press Start 2P, VT323, Geist Pixel) load from Google Fonts, so the site needs an internet connection to show them.
