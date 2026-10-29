# Project context for Claude

## What this is

Cam Klockner's personal portfolio website — a bio page plus a growing list of
his articles. Plain static HTML/CSS, hosted free on GitHub Pages.

**Live at:** https://cklockner54-ux.github.io/Cam_Test-2026-07-24/

## Who you're working with

Cam is 72, retired from a career in construction dewatering, now writing
(including a novel, *WOLF Awakens*). He was competent in BASIC and FORTRAN
~50 years ago (punch-card era) but is new to modern programming and is
learning as we go.

How to work with him:
- Explain what the code does in plain language as you write it — he wants to
  understand the pieces, not just receive them.
- He mostly works from his **phone**, so he can't drag files around or run
  commands locally. Files reach this repo by being attached in chat.
- Show rendered results (screenshots) rather than only describing them.
  Playwright + Chromium are available: `NODE_PATH=$(npm root -g)` and
  `chromium.launch({ executablePath: '/opt/pw-browsers/chromium' })`.

## Structure

```
index.html                  homepage: bio + list of article links
style.css                   shared styling for all pages
images/profile.jpg          his photo (circular frame on homepage)
published/articles/         articles that are live on the site
    *.md                    source content
    *.html                  the styled page the homepage links to
```

Conventions:
- Filenames lowercase-with-dashes (`your-ai-is-only-as-good-as-you-ask.md`).
- `published/` means "ready for the world." Drafts stay out of this repo,
  in his own writing folders. Publishing = adding the file here.
- Each article currently needs both a `.md` (source) and a hand-made `.html`
  (what visitors see). There's no build step yet — converting markdown to
  HTML automatically is a reasonable future improvement.

## Adding an article

1. He attaches the article (PDF, doc, or pasted text).
2. Convert to `published/articles/<slug>.md`, preserving headings and byline.
3. Create `published/articles/<slug>.html` matching the existing article
   page's structure (same stylesheet link `../../style.css`, "Back to home"
   link, `<article>` body).
4. Add a `<li>` link to the Articles section in `index.html`.
5. Commit and push. GitHub Pages redeploys automatically.

## Deployment

GitHub Pages is set to deploy from branch `claude/coding-basics-beginners-mefrlp`,
folder `/ (root)`. Pushing to that branch updates the live site within a
minute or two. The repo is public (required for free Pages).

## Discussed but not done yet

- **More articles** — the immediate next step; he's gathering them.
- **Meta description / SEO** — deliberately deferred until there are more
  articles to write descriptions against. He knows the old
  `<meta name="keywords">` approach is obsolete.
- **Google Search Console submission** — deferred until the site is more
  substantial.
- **Subscribe form** — would need a third-party service (Buttondown,
  Mailchimp) since a static site can't store emails.
- **Likes / comments** — same constraint; giscus (comments stored in GitHub)
  is the natural fit for a site hosted this way.
- **Custom domain** (e.g. `cam-klockner.com`) — he may buy one. Needs DNS
  records at the registrar plus the "Custom domain" field in Pages settings.
- **Auto-posting new articles** to Twitter/X, Facebook, Medium — his original
  longer-term goal. Would use GitHub Actions or a service like Zapier.
- **Repo rename** — the name `Cam_Test-2026-07-24` is leftover from when this
  was a scratch repo. Renaming (e.g. to `cam-klockner`) would clean up the
  URL. He attempted this once and it didn't take; it's purely cosmetic.
