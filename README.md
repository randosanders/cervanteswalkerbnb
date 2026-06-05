# Denker Guest Guide — public web version

A single-page, mobile-friendly guest guide for the short-term rental. Guests reach it by scanning a QR code. It's hosted free on GitHub Pages.

## ⚠️ Privacy rule — read before editing

This repo is **public**. GitHub Pages serves it at a public URL, and pages can be indexed and cached.

**Only general, guest-useful information goes in this repo.** The following NEVER belong here and live only in the in-home printed binder (kept in the private vault):

- Wifi network and password
- Owner cell numbers / personal contact info
- Security-system details: alarms, sensors, cameras, door-code logic
- Anything that signals when the home is empty

If you're tempted to add any of the above to `index.html`, stop. It goes in the printed binder instead.

## Files

- `index.html` — the entire guest guide (self-contained, no dependencies, loads instantly).
- `assets/guest-qr.png` — the QR code guests scan. Points at the published URL.
- `.nojekyll` — tells GitHub Pages to serve the files as-is.

## Deploy (GitHub Pages)

1. Create a **public** repo named `cervanteswalkerbnb` under the personal GitHub account (`randosanders`).
2. Push this folder to it.
3. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
4. The site goes live at `https://randosanders.github.io/cervanteswalkerbnb/` within a minute or two.

## QR code

`assets/guest-qr.png` encodes the published URL. Regenerate it if the URL changes:

```
python3 -m pip install --user "qrcode[pil]"
python3 -c "import qrcode; qrcode.make('https://randosanders.github.io/cervanteswalkerbnb/').save('assets/guest-qr.png')"
```

Print it on the welcome card and/or post it on a wall inside the home.

## Updating content

Edit `index.html` directly and push. Keep wording guest-friendly and keep the privacy rule above in mind. The canonical content (full binder + safety plan) is maintained separately in the private vault; this is the redacted, published cut.
