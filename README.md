# Let Her Rise · Speaker Marketing Kit Site

A single-page static site that bundles every asset in the speaker marketing kit — emails (with live previews + copy buttons), Canva template links, social captions, DM scripts, talking points, email signature snippets, and the press kit one-pager.

Built for the 8 Let Her Rise 2026 speakers to use as a one-stop resource hub.

---

## Deployment to Cloudflare Pages

You have two paths. Pick the one you prefer.

### Option A — GitHub-connected (recommended, matches your usual workflow)

1. Create a new GitHub repo (private is fine — Cloudflare Pages doesn't need it to be public).
2. Push this entire folder to the repo root.
3. In Cloudflare Pages, "Create a project" → connect to GitHub → select the repo.
4. Build settings: **leave everything empty** (no build command, no build output directory — it's a static site).
5. Deploy. You'll get a `*.pages.dev` URL.
6. Custom domain: Pages settings → Custom domains → add `letherrise.elevategrowth.solutions`.
7. DNS: Cloudflare will prompt you to add a CNAME record. Since elevategrowth.solutions is on Cloudflare already, this is a one-click setup.

### Option B — Direct upload (fastest, if you just want it live)

1. Zip this folder.
2. In Cloudflare Pages, "Create a project" → "Direct upload" → drop the zip.
3. Done. Add the custom domain the same way as above.

---

## Before you deploy: fill in these placeholders

### 1. Canva template URLs (in `index.html`)

Search for `href="#"` in `index.html`. You'll find 4 spots, each with a comment like `<!-- TYSEN: replace href="#" -->`. Replace `"#"` with the Canva "Use as Template" URL for each design once you've picked your favorites:

- Email Header template
- IG Square template
- IG/FB Story template
- LinkedIn/FB Horizontal template

### 2. Your contact info (in `index.html`)

Search for `[YOUR NAME]` and `[YOUR EMAIL]` in the footer section. Replace with however you want speakers to reach you for kit questions.

---

## File structure

```
/
├── index.html                          ← the main site
├── README.md                            ← this file (you can delete after deploy)
└── assets/
    ├── emails/
    │   ├── 01-announcement.html         ← email 1 (referenced by iframe + download)
    │   ├── 02-the-talk.html             ← email 2
    │   └── 03-last-call.html            ← email 3
    └── docs/
        ├── let-her-rise-bio-onepager.docx           ← press kit download
        └── let-her-rise-speaker-kit-instructions.docx ← instruction sheet download
```

---

## How the copy buttons work

The "Copy HTML" buttons on the email cards use `fetch()` to grab the email file content and put it on the clipboard. This requires the site to be served from a real web server (Cloudflare Pages, GitHub Pages, or `python -m http.server` locally) — it won't work if you open `index.html` directly with `file://`.

All other copy buttons (captions, DMs, talking points, signature snippets) work everywhere, including locally with `file://`.

---

## Local testing

```bash
# from inside this folder:
python3 -m http.server 8000
# or:
npx serve .
```

Then open `http://localhost:8000` in your browser.

---

## What's included

| Section | What it offers |
|---|---|
| Start Here | Instruction sheet download + the campaign calendar |
| Emails | 3 email templates with live previews, subject lines, copy HTML, and download |
| Graphics | 4 Canva template links (you fill in URLs) |
| Captions | 5 post types × multiple voice variants + hashtag pool |
| DMs | 5 outreach categories including objection handlers |
| Talking Points | 15s/30s/60s + hard ask + FAQ |
| Signature | 2 email signature snippets with live previews + copy HTML |
| Press Kit | One-pager bio download |
| Help | Your contact info for kit questions |

---

Built by Elevate Growth Solutions for the Let Her Rise 2026 speaker cohort.
