# projectreal.gg — Static Clone (School Demonstration)

A local, offline copy of the public website **https://projectreal.gg/**, made to
demonstrate how easily a static front-end can be mirrored. **Educational use only.**

## What this is
- A byte-for-byte copy of the site's *front-end*: HTML, CSS, JavaScript, images,
  fonts references, and videos, exactly as the public server delivered them.
- All navigation between the cloned pages works locally.

## What was intentionally REMOVED
Per the project brief, all **login / registration / account** functionality was
stripped out so this clone cannot act as a credential-collection ("phishing") page:
- The "Sign in" menu, "Create account", and "Dashboard" buttons/links.
- The Discord OAuth login link (`api.projectreal.gg/auth/discord`).
- The account dropdown island in the header.
- `/login`, `/register`, and `/dashboard` URLs were removed from every page,
  including references inside inline scripts (e.g. the pricing "redeem" flow).

## What was changed
- All internal links were **localized**: absolute `https://projectreal.gg/...`
  and language-prefixed `/en/...` links now point at the local copies.
- Only the **default English** site was mirrored. The 14 other language variants
  (de, fr, es, ru, ja, …) were not cloned; the language switcher links fall back
  to the English pages.
- Discord links point to the public invite `https://discord.gg/projectreal`.

## Contents
- `index.html` + `about/`, `pricing/`, `download/`, `docs/`, `privacy/`,
  `terms/`, `resellers/`, `cookies/` — the main pages.
- `docs/` — the full 236-page function reference.
- `_astro/`, `assets/`, `js/` — stylesheets, scripts, images, and videos.

## How to view it
Because pages use root-absolute asset paths (`/_astro/...`), open it through a
local web server rather than double-clicking the file:

```
cd cloned-site
python -m http.server 8099
```
Then visit **http://127.0.0.1:8099/** in a browser.

## Notes / limitations
- The documentation pages are pre-rendered static HTML, so their content shows
  offline. Any feature that talked to the live backend (account status, key
  redemption, live status banner) is inert in this copy — which is expected.
- This copy is a snapshot; it will not update when the real site changes.
