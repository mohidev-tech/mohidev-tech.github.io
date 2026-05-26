# mohidev-tech.github.io

Personal portfolio site — animated, single-file, no build step. Deploys to GitHub Pages from `main`.

## Preview locally

Just open `index.html` in a browser. No build, no server needed.

For a more realistic preview (so the canvas resize handlers behave like on the deployed site):

```bash
# Python 3 — quickest one-liner
python -m http.server 5500
# then open http://localhost:5500
```

## What's in here

| File | Purpose |
|---|---|
| `index.html` | Everything — HTML structure, CSS (theming + animations), JS (typewriter, particles, scroll-reveal, filter, theme toggle, card tilt). ~700 lines, no external JS frameworks. |
| `.nojekyll` | Tells GitHub Pages to skip Jekyll processing — required because we use folders/paths Jekyll would otherwise rewrite. |

## Deploy to GitHub Pages

1. Push this directory to a GitHub repo named **`<your-username>.github.io`** (e.g. `mohidev-tech.github.io`) — that's the magic name GitHub recognizes.
2. Settings → Pages → Source: `Deploy from a branch` → Branch: `main` → `/ (root)`.
3. Live at `https://<your-username>.github.io` within a minute.

## Customization

| Want to change... | Edit |
|---|---|
| Colors / theme | `:root[data-theme="dark"]` and `:root[data-theme="light"]` blocks at the top of the `<style>` |
| Hero tagline rotation | `words` array in the `typewriter()` IIFE |
| Project cards | Each `<a class="project-card">` — `data-tags="..."` controls which filter chips show it |
| Skills | The `.skill-cat` blocks in section 02 |
| Stats numbers | `.about-stats` block in section 01 |

## Stack

- **HTML/CSS/JS** — zero build, zero deps, deploys statically
- **Canvas particle background** — vanilla JS, ~50 lines
- **IntersectionObserver** for reveal-on-scroll
- **CSS variables** for theming (toggle button swaps `data-theme` and `localStorage`)
- **No external JS frameworks**, no React, no bundler. The whole site is one HTML file you can open offline.

## Accessibility

- Respects `prefers-reduced-motion` — disables animations for users who want them off
- Theme toggle saves to `localStorage`
- Semantic HTML (`<nav>`, `<section>`, `<footer>`)
- All links have visible focus states inherited from the browser default + explicit hover styles
