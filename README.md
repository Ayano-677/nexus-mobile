# NEXUS — Mobile AI Chat (Bring Your Own Key)

A small, real AI chat app that runs entirely in the browser. No server, no build step, no sign-up.
Anyone can use it with **their own free Google Gemini API key** — the key is saved only in their own browser and is never part of this code.

![Version](https://img.shields.io/badge/version-1.0-green) ![License](https://img.shields.io/badge/license-MIT-blue) ![No build](https://img.shields.io/badge/build-none-lightgrey)

## Live use

Open `index.html` in any browser — or host the folder on GitHub Pages (see below) and use it from any phone or PC.

## Features

- **Real AI chat** — Google Gemini (`gemini-3.5-flash-lite` by default, `gemini-3.5-flash` optional), with conversation history
- **Bring your own key** — paste your free key once in Settings; a built-in *Test key* button verifies it
- **Notes** — quick notes saved in the browser, with add/delete
- **Explore starters** — one tap starts a guided conversation (AI Studio, Daily Focus, Shortcuts)
- **Working settings** — dark/light appearance actually switches the theme, haptics, notification permission
- **Live home screen** — real clock, real day/date, and a greeting that matches the time of day
- **Private by design** — chat, notes, settings and the API key live only in the visitor's `localStorage`. Nothing is uploaded anywhere except the visitor's own requests to Google's Gemini API
- **No fake replies** — without a key, the app says so honestly instead of pretending to answer

## Get a free Gemini key (30 seconds)

1. Go to [Google AI Studio — API keys](https://aistudio.google.com/apikey) and sign in with a Google account
2. Click **Create API key** and copy it
3. Open NEXUS → **Settings** → paste the key → **Save key** → **Test key**

Free-tier limits apply per Google account/project. If you hit a `429` limit error, wait a bit or use another key/model.

## Run locally

Just open the file:

```bash
# any of these
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

Or serve it (optional):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Publish free on GitHub Pages

1. Create a new GitHub repository (for example `nexus-mobile`) and upload these files (`index.html`, `README.md`, `LICENSE`)
2. Repo → **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)` → Save
3. Your app is live at `https://<your-username>.github.io/nexus-mobile/`

Every visitor uses **their own** key on that page — your key is never shared or exposed.

## Security notes

- **Never commit an API key** to this repo. The app has no key in code on purpose; `.gitignore` also blocks `.env` files.
- A browser app cannot hide a key from its own user — that is fine here, because each visitor uses their own free key, on their own device.
- Revoke a key any time from AI Studio if you pasted it somewhere you don't trust. In NEXUS, **Settings → Remove** deletes it from that browser.

## Project structure

```
nexus-mobile/
├── index.html   # the whole app — UI, styles and logic in one file
├── README.md
├── LICENSE
└── .gitignore
```

## Tech

Plain HTML + CSS + vanilla JavaScript. No frameworks, no dependencies, no build step.

## License

MIT — see [LICENSE](LICENSE). Use it, fork it, make it yours.
