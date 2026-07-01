# Kartik — 3D Portfolio

A React + Vite portfolio with an interactive 3D hero: a floating low-poly
island, orbiting crystal shards, a starfield, and a tiny UI panel — built
with **React Three Fiber** (Three.js for React), animated with
**Framer Motion** for the rest of the page.

This is an original scene (not a copy of any specific Dribbble/tutorial
asset) — the crystals, island, and panel are procedural geometry, so there
are no external 3D model files to manage.

## Run it locally

```bash
npm install
npm run dev
```

Opens at `http://localhost:5173`. Drag inside the hero (desktop only) to
orbit the island; it also auto-rotates on its own.

## Build for production

```bash
npm run build
npm run preview   # preview the production build
```

## Before you deploy — personalize these

1. **`public/Kartik_Resume.pdf`** — swap in your latest resume PDF (same filename,
   or update the two `href="/Kartik_Resume.pdf"` references in `Hero.jsx` and `Contact.jsx`).
2. **`src/data.js`** — set `profile.linkedin` and `profile.github` to your real
   URLs (currently placeholders). Everything else — experience, projects,
   skills, education, certificates — lives here too.
3. Optional: change the color palette in `src/styles.css` (`:root` block —
   `--violet`, `--cyan`, `--amber`) or the accent colors used in `Scene3D.jsx`
   crystals/lights to match.

## A note on performance

Three.js adds real weight (~340KB gzipped). That's normal for a 3D
portfolio and worth it for the effect, but if load time matters more than
the 3D hero on a specific deploy, the simpler code-editor-style version
(no 3D) is a lighter alternative — ask if you'd like that variant again.

## Deploy (free options)

**Vercel** (recommended):
```bash
npm install -g vercel
vercel
```

**Netlify:** drag the `dist/` folder (after `npm run build`) onto
https://app.netlify.com/drop, or connect the repo with build command
`npm run build` and publish directory `dist`.

Once live, put the URL on your resume next to your name.

## Tech stack

- React 19 + Vite
- `three`, `@react-three/fiber`, `@react-three/drei` — the 3D scene
- `framer-motion` — scroll-reveal animations on the rest of the page
- Plain CSS with a design-token system, no UI framework

## Project structure

```
src/
  components/
    Scene3D.jsx        the 3D canvas: island, crystals, ring, panel, stars
    Hero.jsx             overlay text + CTA on top of the canvas
    Nav.jsx                scroll-spy navigation
    Reveal.jsx               scroll-into-view animation wrapper
    StatStrip.jsx
    Experience.jsx
    Projects.jsx
    Skills.jsx
    EducationCerts.jsx
    Contact.jsx
    Footer.jsx
  data.js                 <- all your content lives here
  styles.css               <- design tokens + all styling
  App.jsx                    <- wires sections + active-tab tracking
```
