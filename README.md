# Vanguard Damage Calculator

A small single-page web app for tracking unit power values during a *Cardfight!! Vanguard* match. Tap buttons to accumulate power on each of six board slots, then reset per-slot or all at once at the end of a turn.

## Tech stack

- [Vue 3](https://vuejs.org/) — UI framework
- [Vite](https://vitejs.dev/) — dev server and build tool
- [Bootstrap 5](https://getbootstrap.com/) — base CSS

## Getting started

```bash
npm install      # install dependencies
npm run dev      # start the local dev server
npm run build    # build for production (outputs to dist/)
npm run preview  # preview the production build locally
```

## How it works

The entry point [index.html](index.html) loads [src/main.js](src/main.js), which creates the Vue app, imports Bootstrap's CSS, and mounts [App.vue](src/App.vue). `App.vue` renders the single [Calculator](src/components/Calculator.vue) component, where all the logic lives.

The calculator tracks six independent power counters in a `inputValues` array:

- **+10000 / +5000 / +2000** — add the given power to that slot.
- **Clear** — reset that single slot to 0.
- **End Turn** — reset all six slots to 0.

## Deployment

`vite.config.js` sets `base: '/vgdamcal/'`, so the build is served from the `/vgdamcal/` subpath (e.g. GitHub Pages). The built assets live in `dist/`.

## Project structure

```
vgdamcal/
├── index.html                    # HTML entry point
├── vite.config.js                # Vite config (base path, Vue plugin)
├── src/
│   ├── main.js                   # App bootstrap
│   ├── App.vue                   # Root component
│   ├── components/
│   │   └── Calculator.vue        # All calculator logic + styles
│   └── assets/                   # Images (background, logos)
└── dist/                         # Production build output
```
