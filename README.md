# treeguytrenton.com

Static one-page site for **Tree Guy LLC** (Breckenridge / Summit County, CO).
No build step, no framework — plain HTML/CSS/JS. Edit `index.html` and push.

## Structure
```
index.html          the whole site (styles + scripts inline)
CNAME               custom domain for GitHub Pages
favicon.svg  robots.txt  sitemap.xml
media/
  hero.mp4          desktop hero (720p)
  hero-mobile.mp4   phone hero (480p, auto-selected)
  hero-poster.jpg   first frame / social preview
  ba/               10 before+after job pairs
  clips/            service clips + long-form ad
```

## Deploy
Hosted on **GitHub Pages** from the `main` branch. Push to `main` = live in ~1 minute.
DNS stays at Squarespace (registrar only) pointing at GitHub's IPs.

## Editing notes
- **Swapping media:** change the *filename* (e.g. `-v2`) rather than overwriting,
  otherwise browsers keep serving the cached old file.
- **Before/after pairs:** add `media/ba/jobN-before.jpg` + `jobN-after.jpg`, then add
  `{n:N,o:'portrait'}` (or `'landscape'`) to the `jobs` array in `index.html`.
- **Raw footage is NOT in this repo** — originals live outside it. Keep it that way.

## Connecting the quote form (required before launch)
GitHub Pages is static, so the form needs an external handler.

1. Go to **formspree.io**, sign up, create a form, set the destination to
   `treeguytrenton@gmail.com`.
2. Copy the endpoint it gives you, e.g. `https://formspree.io/f/abcdwxyz`.
3. In `index.html`, find `action="https://formspree.io/f/FORM_ID"` and replace
   `FORM_ID` with your ID. That is the only edit needed.
4. Push, then submit a real test from the live site. Formspree emails a one-time
   confirmation link on the first submission — click it or nothing forwards.
5. Confirm the test arrives, including the phone number and message.

Until step 3 is done the form shows "Form not connected yet" instead of failing silently.
A hidden honeypot field blocks most spam bots. Free tier is 50 submissions/month.

## Still to do before launch
- Replace the placeholder logo (currently the fir + "tree guy" wordmark).
- Re-check review counts (last verified June 2026).
