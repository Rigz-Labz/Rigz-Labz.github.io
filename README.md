# Rigz Labz website

**Live at: https://rigz-labz.github.io**

Instagram: https://www.instagram.com/p_rigz/ · Hevy: https://hevy.com/user/prigz

The home of **Rigz Labz**, my personal projects. Each tool has its own page; the tools themselves live in separate private repos, and this repo only holds the public website.

| Page | Tool | Data source | Tool repo |
|---|---|---|---|
| `index.html` (home) | **Rigz Liftz**, my gym dashboard: Hevy workouts into stats, a dashboard and Instagram cards | Hevy API (not affiliated with or endorsed by Hevy) | `Rigz-Labz/rigz-liftz` |
| `arrowz.html` | **Rigz Arrowz**, my archery practice: handicaps, grouping, a dashboard and cards | Archery Success exports (not affiliated with or endorsed by Archery Success) | `Rigz-Labz/rigz-arrowz` |

The home page stays the Liftz page because the Google sign-in for its story-cards job points at it (see below). Each page ends with a link to the other tools.

## What's here

| File | What it is |
|---|---|
| `index.html` | Rigz Liftz: how it works, the GitHub Actions gym-to-story flow, the cards, the dashboard, then "More from Rigz Labz" |
| `arrowz.html` | Rigz Arrowz: how it works, reading the plotted arrows, the cards, the dashboard |
| `privacy.html` | Privacy policy |
| `style.css` | Styles for both pages (black, `#00FF00` green, `#B47CFF` violet) |
| `img/` | Web-sized copies of cards and dashboard screenshots, the logo, favicon and link preview (`og.png`) |
| `fonts/Figtree.ttf` | Figtree font, self-hosted (SIL Open Font License, see `fonts/OFL.txt`) |

## Logos

- `img/logo-labz.png` (RIGZ + beaker): **Rigz Labz**, the parent brand. In the site header.
- `img/logo-liftz.png` (RIGZ + dumbbell): **Rigz Liftz**, the gym tool. In the footer of the Liftz page.
- `img/logo-arrowz.png` (RIGZ + compound bow, my own artwork): **Rigz Arrowz**, the archery tool. In the footer of the Arrowz page and on its "More from Rigz Labz" link.

The header always carries the Rigz Labz logo; each tool's own section or page uses its own logo. The logo versions are made by `assets/make_logo_variants.py` in the `rigz-liftz` repo.

## Don't break these

The Google sign-in for the story-cards job (Google Cloud project **Rigz Liftz**, project ID `rigz-hevy`, which Google doesn't allow to be changed; Branding page) points at:

- Home page: `https://rigz-labz.github.io`
- Privacy policy: `https://rigz-labz.github.io/privacy.html`
- Authorised domain: `rigz-labz.github.io`

Keep both pages online and keep the link to `privacy.html` on the home page, or Google can stop accepting the app.

## Updating

- **Stats** on the page are typed in by hand and frozen at a date (shown under the numbers). Update the numbers and the "as of" date together.
- **Images** come from each tool: generate cards or screenshots in `rigz-liftz` (on the Mac: `~/hevy-local`) or `rigz-arrowz` (`~/rigz-arrowz`; its images are named `arrowz-*`), save them into `img/` as WebP (cards 720 px wide, screenshots 1400 px), and keep the `width`/`height` attributes in `index.html` matching.
- **Never publish** API keys, workout times or locations, other people's names, or anything from the private repo's `data/` or `.env`.

Preview locally:

```bash
python3 -m http.server 8600 --bind 127.0.0.1
```

then open http://127.0.0.1:8600. Pushing to `main` publishes the site; GitHub Pages usually updates within a minute or two.
