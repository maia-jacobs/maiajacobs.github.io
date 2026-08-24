# Academic website starter

A plain HTML/CSS site (no build step, no framework) meant to be hosted for
free on GitHub Pages. Every page has placeholder text in `[brackets]` —
replace it with your own content before you publish.

## Pages

| File | Purpose |
|---|---|
| `index.html` | Home / About |
| `research.html` | Research overview and current projects |
| `publications.html` | Publication list |
| `teaching.html` | Courses and advising |
| `cv.html` | CV summary + a download button for `files/cv.pdf` |
| `contact.html` | Email, office, social links |

Shared styles are in `css/style.css`; the only script (`js/main.js`) just
handles the mobile menu toggle. `.nojekyll` tells GitHub Pages to serve the
files as-is.

## 1. Edit the content

Open each `.html` file and replace the bracketed placeholders — name, title,
university, bio, projects, courses, publications, contact details. The
`<title>` tag and nav header ("Jane A. Researcher") appear on every page, so
use find-and-replace across all files once you land on your real name.

Add your CV as `files/cv.pdf` (exact filename) so the download button on the
CV page works. Replace `images/avatar-placeholder.svg` with a real photo if
you'd like one — any image works, just update the `src` on `index.html`.

## 2. Put it on GitHub

If you're comfortable with git:

```bash
cd academic-website
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Prefer the web UI? Create a new repository at github.com/new, then drag the
whole folder's contents into the "upload files" screen and commit.

**Choosing a repo name matters:**
- Name the repo `<your-username>.github.io` (exactly, replacing
  `<your-username>` with your actual GitHub username) and your site
  publishes at `https://<your-username>.github.io/` — no extra path.
- Any other repo name (e.g. `academic-website`) still works, but the site
  publishes at `https://<your-username>.github.io/<repo-name>/`.

## 3. Turn on GitHub Pages

In the repo on GitHub: **Settings → Pages → Build and deployment → Source**,
select **Deploy from a branch**, then pick branch `main` and folder `/ (root)`,
and save. GitHub builds and publishes the site — this usually takes under a
minute, and the same Pages settings page will show you the live URL once
it's ready.

Any time you push new commits to `main`, the live site updates automatically
within a minute or two.

## 4. Optional: custom domain

If you own a domain and want e.g. `www.janeresearcher.com` instead of the
`github.io` address, add a `CNAME` file to the repo root containing just your
domain, then point your domain's DNS at GitHub Pages (GitHub's docs walk
through the exact DNS records: docs.github.com → Pages → custom domain).
GitHub Pages also provides free HTTPS for custom domains once DNS is
verified.

## Notes

- This is plain HTML — no Jekyll, no npm, nothing to install. Editing and
  redeploying is just: edit the `.html` file, commit, push.
- Each page repeats its own header/nav/footer (since there's no templating
  without Jekyll). If you rename a page or add a new one, update the `<nav>`
  block in every other file to match.
- The design uses Google Fonts (Source Serif 4) loaded from
  `fonts.googleapis.com`; if you'd rather not depend on an external font
  host, delete the two `<link>` tags in each page's `<head>` and the site
  will fall back to system fonts automatically.
