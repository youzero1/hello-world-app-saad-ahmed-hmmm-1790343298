---
status: pending
title: Hello World App — single centered greeting page with language cycling
---

1. Scaffold the base project files if they do not exist: `index.html`, `package.json`, `vite.config.ts`, `tsconfig.json`, `src/main.tsx`. Configure the Vite plugins `@tailwindcss/vite` and `@tanstack/router-plugin/vite`, and register the `@/` alias pointing at `src/`. Expected outcome: `npm run dev` starts a blank but working app with routing and Tailwind wired up.

2. Create `src/styles/global.css` containing exactly the Tailwind v4 import as its first line, and import it once from `src/main.tsx`. Expected outcome: Tailwind utility classes take effect anywhere in the app.

3. Create the app shell at `src/routes/__root.tsx`: a root route rendering an outlet inside a full-height wrapper that applies the page background (subtle vertical gradient, light neutral tones) and the base text colour. Expected outcome: every route inherits the background and fills the viewport height.

4. Create the home route at `src/routes/index.tsx` rendering a single centered section: an oversized responsive "Hello World" heading, a short muted subtitle line beneath it, and a primary action button below. Center with flex utilities both axes; scale type with responsive Tailwind size steps so it reads well from small phones to large desktops. Expected outcome: visiting `/` shows the finished greeting page.

5. Add the greeting data in `src/lib/greetings.ts`: an ordered, readonly array of about six greetings, each with the greeting text, its language label, and a stable id. Expected outcome: a single typed source of truth for the greeting cycle.

6. Add the interaction in `src/components/GreetingHero.tsx` (used by `src/routes/index.tsx`): hold the current index in local state, render the current greeting as the heading and the language label in the subtitle, and have the button advance the index with wraparound back to the first entry. Expected outcome: each click shows the next language and the cycle loops forever.

7. Polish: add a short fade/translate transition on the heading when the greeting changes (keyed re-render plus Tailwind animation utilities), give the button hover/active/focus-visible states, and confirm no horizontal overflow at narrow widths. Expected outcome: the page feels finished and is keyboard accessible.

8. Verify: run the dev server, click through the full cycle at least one full loop, and check the layout at mobile, tablet and desktop widths. Expected outcome: no console errors, no type errors, correct centering at all sizes.
