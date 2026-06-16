# 🏋️ Back to the Bar — Workout Tracker

An adaptive 6-week gym reboot app for returning lifters. Logs weights in kg and lb, adjusts your schedule when you miss a day, and remembers everything between sessions.

---

## Features

- **6-week progressive plan** across three phases: Foundation → Build → Progress
- **Pick your workout days** — choose specific days of the week (e.g. Mon / Wed / Fri), not just a count
- **Smart missed-session handling** — if you skip a day, that session shifts forward automatically; nothing is lost or stacked
- **Weight logging per exercise** — enter weights in kg or lb with live conversion between the two
- **Last-session suggestions** — shows what you lifted previously so you know when to go heavier
- **Streak + session counter** — tracks consecutive completed sessions
- **Session history** — browse past workouts with weights logged per exercise
- **Persistent storage** — all data saved locally; nothing sent to any server

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18 or later
- npm v9 or later

### Install & run

```bash
# 1. Clone the repo
git clone https://github.com/your-username/workout-tracker.git
cd workout-tracker

# 2. Install dependencies
npm install

# 3. Start the dev server
npm run dev
```

Then open [http://localhost:5173](http://localhost:5173) in your browser.

### Build for production

```bash
npm run build
# Output goes to ./dist — deploy anywhere (Vercel, Netlify, GitHub Pages, etc.)
```

---

## Project Structure

```
workout-tracker/
├── index.html              # HTML entry point
├── vite.config.js          # Vite config
├── package.json
└── src/
    ├── main.jsx            # React root + window.storage shim
    ├── index.css           # Base styles
    └── WorkoutApp.jsx      # Main app (single-file component)
```

### Storage

The app uses `window.storage` — a key/value API provided by Claude's artifact environment. When running standalone (outside Claude), `src/main.jsx` provides a shim that maps it to `localStorage`, so data persists in the browser automatically.

---

## Workout Plan

| Phase | Weeks | Style | Days/week |
|---|---|---|---|
| Foundation | 1–2 | Full body A/B | 2–3 |
| Build | 3–4 | Full body A/B/C | 3–4 |
| Progress | 5–6 | Push / Pull / Legs | 3–5 |

Switch phases manually in the app when you feel ready to progress.

---

## Customisation

All workout data lives in the `PHASES` constant at the top of `WorkoutApp.jsx`. To add, remove, or rename exercises, edit the `sessions` arrays inside each phase. Each exercise accepts:

```js
{ name: 'Exercise name', target: '3 × 10', hasWeight: true }
```

Set `hasWeight: false` for cardio, planks, or bodyweight-only movements.

---

## Tech Stack

- [React 18](https://react.dev/)
- [Vite](https://vitejs.dev/)
- [Tailwind CSS](https://tailwindcss.com/) (via CDN utility classes)
- [Lucide React](https://lucide.dev/) icons
- [Google Fonts](https://fonts.google.com/) — Oxanium + Inter

---

## License

MIT
