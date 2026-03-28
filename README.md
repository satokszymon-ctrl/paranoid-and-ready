# PARANOID AND READY

Gear, guides AND gifts for the prepared mind.

A curated preparedness gear site — calm, practical recommendations without the survivalist noise.

**Live:** [paranoidandready.com](https://paranoidandready.com)

## Stack

- Static HTML / CSS / vanilla JS
- Hosted on **GitHub Pages**
- Fonts: **JetBrains Mono** only
- Monetization: Amazon Associates
- No build step required (Vanilla HTML Structure)

## Deployment

Push to `main` → GitHub Actions automatically deploys the site to GitHub Pages via the `.github/workflows/deploy.yml` action.

## Structure

The site follows a strict flat-hierarchy structure organized into logical folders. All CSS is centralized, and all links use absolute root-relative paths.

```text
/
├── index.html                   ← Homepage / Landing
├── about.html                   ← About page
├── contact.html                 ← Contact page
├── guides.html                  ← Central hub for all guides
├── 404.html                     ← Custom 404 error page
├── CNAME                        ← Custom domain for GitHub Pages
│
├── /css/
│   └── style.css                ← Unified stylesheet for the entire site
│
├── /categories/                 ← Core gear and product round-ups
│   ├── energy-power.html
│   ├── water-hydration.html
│   └── ...
│
├── /guides/                     ← Long-form educational content and checklists
│   ├── guide-evacuation-bags.html
│   ├── guide-first-aid-kits.html
│   └── ...
│
└── /scenarios/                  ← Situation-specific situational prep
    ├── power-outage.html
    ├── medical-emergency.html
    └── ...
```

## Local Development

Because all internal links are root-relative (`href="/categories/energy-power.html"`), opening the HTML files directly in your browser (`file:///...`) will break the styling and links.

To preview the site locally, navigate to the folder in your terminal and run a local python server:

```bash
python3 -m http.server
```

Then visit `http://localhost:8000` in your web browser.

## Contributing / Modifying

1. **Design:** ALWAYS reference `visual_identity.md`. The design language is strict (Concrete bunker, JetBrains Mono, dried blood red #8B0000).
2. **CSS:** Modifying `/css/style.css` updates the entire site. No inline `<style>` blocks are allowed.
3. **Paths:** New links to pages must start with `/` (e.g., `<a href="/guides/guide-safes.html">`).
4. **Copywriting:** No ampersands (`&`), no em-dashes (`—`), no exclamation marks. See `visual_identity.md` for voice guidelines.
