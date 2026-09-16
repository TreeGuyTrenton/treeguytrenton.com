# treeguytrenton.com

Website for **Tree Guy LLC** — tree removal, fire mitigation and storm response in
Breckenridge and Summit County, Colorado.

A single static page. No build step, no framework — plain HTML, CSS and JavaScript,
all inline in `index.html`.

## Structure

```
index.html          the whole site (styles + scripts inline)
CNAME               custom domain
favicon.svg  robots.txt  sitemap.xml
media/
  hero.mp4          desktop hero video (720p)
  hero-mobile.mp4   phone hero (480p, chosen automatically)
  hero-poster.jpg   first frame, also the social share image
  logo/             logo lockup, monogram, ISA badge, favicon (SVG)
  ba/               before + after job photos
  clips/            service clips and the long-form film
```

## Deploying

Hosted on GitHub Pages from the `main` branch — pushing to `main` publishes in about
a minute. DNS is managed at Squarespace, which acts as registrar only and points at
GitHub's servers.

## Making changes

**Swapping a photo or video:** change the *filename* (e.g. `-v2`) rather than
overwriting the old one. Browsers cache aggressively and will keep serving the old
file if the name stays the same.

**Adding a before/after pair:** drop `media/ba/jobN-before.jpg` and `jobN-after.jpg`
into place, then add `{n:N,o:'portrait'}` (or `'landscape'`) to the `jobs` array in
`index.html`. Captions, dots and the counter update themselves.

**Video sizing:** hero clips are kept small on purpose — mountain cell service is
slow. Keep replacements at 720p or below and re-compress before committing.

**Source footage** is deliberately not in this repo. Originals are archived
separately; only web-optimised files belong here.

## Quote form

The form posts to Formspree, since GitHub Pages can't run server-side code.
Submissions forward to the business inbox. A hidden honeypot field filters most
spam bots. If submissions ever stop arriving, check the Formspree account first —
the free tier has a monthly limit.
