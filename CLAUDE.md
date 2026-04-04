# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install        # install dependencies
npm run dev        # start Vite dev server at http://localhost:5173
npm run build      # build to dist/
npm run lint       # run ESLint
npx serve dist --listen 3000  # serve the production build statically (alternative if dev server has issues)
```

## Architecture

Single-file React app — all logic lives in [src/App.jsx](src/App.jsx). No routing, no global state library, no backend.

- State is managed with `useState` in `App` (transactions list + form fields + filter state)
- `index.html` → `src/main.jsx` (entry point) → `src/App.jsx` (entire app)
- Styles: `src/index.css` (global), `src/App.css` (component-scoped by convention but not CSS modules)

## Known Issues (intentional — part of the course)

- `amount` is stored as a string, so `reduce` on amounts concatenates instead of summing (bug)
- UI is intentionally rough
- Code is intentionally messy/unstructured
