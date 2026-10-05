# FitLife & Fuel 🏋️

A single-file, offline-first web app for tracking nutrition, daily fitness habits, and gym progress — with an AI coach and a community feed.

![Status](https://img.shields.io/badge/status-active-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Made with](https://img.shields.io/badge/made%20with-vanilla%20JS-yellow)

## ✨ Features

- **Fuel Tracker** — log meals by category (breakfast / lunch / dinner / snacks), track calories, protein, carbs, and fats against daily targets
- **365-Day Journal** — clickable calendar to log workouts, mindset wins, water intake, sleep hours, and a daily mood rating
- **Gym Showroom** — a local social feed where you post PRs, progress milestones, and gym selfies, with hype reactions and comments
- **Coach Frank** — a floating AI fitness assistant that answers questions about splits, macros, and recovery
- **Dark / light mode** — persisted to `localStorage`
- **Zero build step** — one `index.html`, no npm, no bundler, no framework

## 🚀 Quick Start

### Just want to use it
Download `index.html` and open it in any modern browser. That's it.

### Run it locally with a server (recommended)
```bash
# Python 3
python -m http.server 8000

# or Node
npx serve .
```
Then visit http://localhost:8000

### Deploy to GitHub Pages
1. Push this repo to GitHub
2. **Settings → Pages → Source: Deploy from a branch → main / (root)**
3. Your app is live at `https://YOUR-USERNAME.github.io/fitlife-fuel/`

## 🧠 Enabling Live AI Responses (optional)

By default, Coach Frank uses a built-in offline advice engine (instant, no key required).

To enable live Google Gemini responses:
1. Get a free API key at https://aistudio.google.com/apikey
2. Open `index.html`
3. Find this line near the bottom of the `<script>` block:
   ```js
   const COACH_API_KEY = '';
   ```
4. Paste your key inside the quotes
5. Refresh the page

> ⚠️ **Security note:** Never commit your API key to a public repo. For a real deployment, proxy the request through a small backend (Cloudflare Worker, Vercel Function, etc.) and keep the key server-side.

## 🗂 Project Structure

```
fitlife-fuel/
├── index.html      # The entire app (HTML + Tailwind via CDN + JS)
├── README.md       # You are here
└── .gitignore
```

## 💾 Data Storage

All data is stored **locally in your browser** via `localStorage`. Nothing is sent to a server (except optional Coach Frank requests when you provide an API key).

| Key | Contents |
|---|---|
| `fitlife_user_profile` | Name, goal, calorie & protein targets |
| `fitlife_meals` | All logged food entries |
| `fitlife_journal` | All journal day entries |
| `fitlife_posts` | Showroom feed posts and comments |
| `fitlife_theme` | `"dark"` or `"light"` |

To wipe everything: open DevTools → Application → Local Storage → delete the `fitlife_*` keys.

## 🛠 Tech Stack

- **HTML5 / CSS3 / vanilla JavaScript** — no framework, no build step
- **[Tailwind CSS](https://tailwindcss.com/)** via CDN (with custom config)
- **[Font Awesome 6](https://fontawesome.com/)** for icons
- **[Google Fonts — Inter](https://fonts.google.com/specimen/Inter)**
- **[Google Gemini API](https://ai.google.dev/)** (optional, for Coach Frank)

## 🐛 Known Limitations

- Data is per-browser and per-device (no sync across devices yet)
- Coach Frank's live mode requires your own API key
- Showroom feed is local-only — posts aren't shared with other users yet
- Uses CDN dependencies, so it requires an internet connection on first load

## 🗺 Roadmap

- [ ] Export / import data as JSON
- [ ] Optional cloud sync (Supabase / Firebase)
- [ ] Real multi-user showroom
- [ ] Progress charts (weight, PRs over time)
- [ ] PWA support with offline caching

## 🤝 Contributing

Issues and PRs are welcome. If you're adding a feature, please keep the "single file, no build step" philosophy — it's the whole point of this project.

## 📄 License

MIT — see below.

```
MIT License

Copyright (c) 2026 YOUR NAME

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
