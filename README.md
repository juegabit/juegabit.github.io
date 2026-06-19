# juegabit.github.io

Public site for **Juegabit** (a brand of ITCSUY SRL) and its games. Plain static HTML —
hosted free on GitHub Pages. Serves the studio landing page plus a per-game folder with a
home page and privacy policy (used for app-store + Google OAuth requirements).

```
/
├── index.html              studio landing (lists games)
├── assets/                 shared css, logo, favicons
└── pixel-quest/
    ├── index.html          game home page
    └── privacy.html        game privacy policy
```

## One-time deploy

1. Create a free GitHub **organization** named `juegabit`
   (https://github.com/account/organizations/new — this claims `juegabit.github.io`).
2. In that org, create a **public** repo named exactly `juegabit.github.io`.
3. Push these files to the `main` branch:
   ```bash
   cd juegabit.github.io
   git init && git add -A && git commit -m "Juegabit site + Pixel Quest privacy policy"
   git branch -M main
   git remote add origin https://github.com/juegabit/juegabit.github.io.git
   git push -u origin main
   ```
4. Repo → **Settings → Pages** → Source: *Deploy from a branch*, branch `main` / `/ (root)`.
   The site goes live at **https://juegabit.github.io/** within ~1 minute.

## URLs to paste into Google (OAuth Branding page)

- **Application home page:** `https://juegabit.github.io/pixel-quest/`
- **Privacy policy link:** `https://juegabit.github.io/pixel-quest/privacy.html`
- **Authorized domain:** `juegabit.github.io`

## Google Search Console verification

Add a property for `https://juegabit.github.io/` (URL-prefix). Use the **HTML tag** method:
copy the `<meta name="google-site-verification" ...>` tag into the `<head>` of `index.html`
(there's a commented placeholder ready), commit, push, then click *Verify*.

## Adding the next game

1. Copy `pixel-quest/` to a new folder, e.g. `cosmic-pop/`.
2. Drop the game icon in `assets/` and update the two HTML files (title, copy, icon path).
3. Add a card for it in the root `index.html`.
4. Reuse the same privacy policy structure (swap the game name).

The contact email (`pablo.caviglia@gmail.com`) and entity (ITCSUY SRL) are in the footers and
the privacy policy — change in one place per file if needed.
