# RIGZ Hevy website

**Live at: https://p-rigz.github.io**

A one-page showcase for RIGZ Hevy, my personal tool that turns my Hevy workouts into stats, a dashboard and Instagram cards, plus the privacy policy for its Google sign-in. The tool itself lives in a separate private repo (`P-Rigz/hevy-local`); this repo only holds the public website.

## What's here

| File | What it is |
|---|---|
| `index.html` | The showcase page: how it works, the GitHub Actions gym-to-story flow, the cards, the dashboard |
| `privacy.html` | Privacy policy |
| `style.css` | Styles for both pages (black, `#00FF00` green, `#B47CFF` violet) |
| `img/` | Web-sized copies of cards and dashboard screenshots, the logo, favicon and link preview (`og.png`) |
| `fonts/Figtree.ttf` | Figtree font, self-hosted (SIL Open Font License, see `fonts/OFL.txt`) |

## Don't break these

The Google sign-in for the story-cards job (Google Cloud project **RIGZ Hevy**, Branding page) points at:

- Home page: `https://p-rigz.github.io`
- Privacy policy: `https://p-rigz.github.io/privacy.html`
- Authorised domain: `p-rigz.github.io`

Keep both pages online and keep the link to `privacy.html` on the home page, or Google can stop accepting the app.

## Updating

- **Stats** on the page are typed in by hand and frozen at a date (shown under the numbers). Update the numbers and the "as of" date together.
- **Images** come from the tool: generate cards or screenshots in `hevy-local`, save them into `img/` as WebP (cards 720 px wide, screenshots 1400 px), and keep the `width`/`height` attributes in `index.html` matching.
- **Never publish** API keys, workout times or locations, other people's names, or anything from the private repo's `data/` or `.env`.

Preview locally:

```bash
python3 -m http.server 8600 --bind 127.0.0.1
```

then open http://127.0.0.1:8600. Pushing to `main` publishes the site; GitHub Pages usually updates within a minute or two.
