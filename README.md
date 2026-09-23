# Maia Jacobs — personal site

A plain HTML/CSS site (no build step, no framework) meant to be hosted for
free on GitHub Pages, built from your CV and the NU-PATH Lab website.

## Pages

| File | Purpose |
|---|---|
| `index.html` | Home / About — bio, research focus tags, lab callout, news |
| `research.html` | NU-PATH themes, the 6 active projects, team-science grants, selected funding |
| `publications.html` | Full journal &amp; conference list (J1&ndash;J34) + book chapter |
| `teaching.html` | Northwestern &amp; Georgia Tech courses, lab advising roster |
| `cv.html` | Appointments, education, awards, selected funding, selected service + download button for `files/cv.pdf` |
| `contact.html` | Email, department, office address, lab link |

Shared styles are in `css/style.css`; the only script (`js/main.js`) just
handles the mobile menu toggle. `.nojekyll` tells GitHub Pages to serve the
files as-is. Your real CV is already sitting at `files/cv.pdf` — the
"Download full CV" button on the CV page points straight to it.

## 1. A few things worth double-checking before you publish

- **Photo:** I couldn't fetch your lab headshot automatically (the site
  blocks that kind of direct download), so `images/avatar-placeholder.svg`
  is currently a plain "MJ" monogram. Swap in a real photo any time — drop
  an image file into `images/` and update the `src` on the `.hero-portrait`
  `<img>` tag on `index.html`.
- **Other links:** Google Scholar, GitHub, LinkedIn, or Bluesky/X aren't
  linked anywhere since I didn't have confirmed URLs for them — add them to
  the `.hero-links` on `index.html` and/or the contact list on
  `contact.html` whenever you'd like.
- **News section:** the four items on the home page are real but
  hand-picked — update them as things change (new papers, awards, grants).
- **Publications:** the full journal/conference list and one book chapter
  are included. Workshop papers, extended abstracts, and posters were left
  out for length — the full CV PDF has everything.
- **Funding:** `research.html` and `cv.html` only list awarded PI/Co-PI
  grants from your CV, not items marked "In Review" or "Submitted,
  Unfunded" — update these as those move from pending to funded.

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
- The design uses Google Fonts (Fraunces, Work Sans, JetBrains Mono) loaded
  from `fonts.googleapis.com`; if you'd rather not depend on an external
  font host, delete the `<link>` tags in each page's `<head>` and the site
  will fall back to system fonts automatically.
