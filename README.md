# Swiftly — team website

A single-page site for the Swiftly STEM Racing team. Plain HTML, CSS and JavaScript — no build
step, no frameworks, no npm. Open it and it runs.

The site leads with the team — who Swiftly is, the six members, and the working rules the team
holds itself to — then covers the car, the competition and the route to the World Finals.

Nothing on it is invented. The names and the team photo are the team's own. Facts about the
competition are sourced from the official STEM Racing sites and listed at the bottom of the page.
No results, race times, awards or sponsors are claimed, because there are none yet.

See **NEXT-STEPS.md** for what to add as you gather your own content.

## Files

```
index.html            the whole page
css/styles.css        all styling (brand colours at the very top)
js/main.js            nav, scroll effects, counters
images/team/          the team photo, at two sizes for responsive loading
images/logo.svg       placeholder team mark — replace with your own
images/favicon.svg    browser tab icon — replace with your own
NEXT-STEPS.md         what to add later, and what to verify first
```

One photograph is used, in the hero. The car and the race track are hand-drawn inline SVG
diagrams, so they scale perfectly and cost nothing to load.

## Viewing it

Double-click `index.html`. That is enough for everything except the Google Fonts, which need an
internet connection (there are sensible fallback fonts if you are offline).

If you'd rather run a local server:

```powershell
# from this folder, with Python installed
python -m http.server 8000
# then open http://localhost:8000
```

## Changing the brand colours

Everything keys off three values at the top of `css/styles.css`:

```css
--accent:     #22E0C8;   /* Swiftly teal — buttons, links, diagrams, highlights */
--accent-2:   #FFB020;   /* amber accent */
--accent-ink: #04231F;   /* text colour on top of --accent */
```

Change those and the whole site follows, diagrams included. `--ink`, `--surface` and `--text` just
below control the dark background and body text.

## Before you rely on the technical figures

Minimum weight, wing dimensions and race format are all set by the technical regulations, and
those are revised each season. Check the current rulebook and correct the spec table if anything
has changed. This is the first item in NEXT-STEPS.md.

## Putting it online (free options)

| Option | Good for | How |
|---|---|---|
| **GitHub Pages** | Free, custom domain, version history | Push this folder to a repo, then Settings → Pages → deploy from `main` |
| **Netlify Drop** | Fastest — no account needed to try | Drag this folder onto [app.netlify.com/drop](https://app.netlify.com/drop) |
| **Cloudflare Pages** | Free, very fast | Connect a GitHub repo, no build command needed |

All three work with a static site like this one, and all three let you point a domain at it later.

## Accessibility & performance notes

- Semantic landmarks, a skip link, visible focus rings, and descriptive `aria-label`s on both SVG
  diagrams so screen readers get a real description rather than silence.
- All animation is disabled under `prefers-reduced-motion`.
- The team photo is served at two sizes via `srcset`, so phones download 74 KB rather than 228 KB.
- The whole page is around 300 KB loaded, so it is fast on a school connection.
