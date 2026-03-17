# 🎵 NoteRead — Music Sight Reading PWA

A progressive web app for learning to read sheet music — playable directly in the browser, installable on any phone.

## Features

- **🎮 Game Modes** — Landmark Notes, Line Notes, Space Notes, Full Staff, Custom Sets
- **📷 AI Sheet Music Scanner** — Take a photo of any sheet music; Claude AI extracts all notes and saves them as a practice set
- **🎼 Auto-Tuning Calibration** — Listens to the first note you play and auto-detects your instrument's transposition. Works with:
  - Instruments slightly off concert pitch
  - Bb instruments (clarinet, trumpet) → +2 semitones
  - Eb instruments (alto sax) → +3 semitones
  - Guitar (octave transposer) → +12 / −12 semitones
- **🔊 Sound Feedback** — Web Audio API tones for correct / wrong answers and game completion
- **⭐ Progress Tracking** — Stars, accuracy %, best times, notes read — saved in localStorage
- **📱 PWA** — Installable on Android and iOS via "Add to Home Screen"

## Tech Stack

- Pure HTML / CSS / JavaScript — zero dependencies, zero build step
- Web Audio API (synthesized tones, no audio files)
- `getUserMedia` + autocorrelation (YIN algorithm) for real-time pitch detection
- Anthropic Claude API (`claude-sonnet-4-20250514`) for sheet music image analysis
- Service Worker for offline support

## Deploy to GitHub Pages (free hosting)

1. Fork or push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to **Deploy from branch → main → / (root)**
4. Your app will be live at `https://<your-username>.github.io/<repo-name>/`

## Deploy to Netlify (instant, drag & drop)

1. Go to [netlify.com/drop](https://netlify.com/drop)
2. Drag the project folder onto the page
3. Done — live URL in seconds

## Install on Android

1. Open the live URL in Chrome
2. Tap the three-dot menu → **Add to Home Screen**
3. The app installs and launches full-screen with no browser chrome

## Install on iOS

1. Open the live URL in Safari
2. Tap the Share button → **Add to Home Screen**

## API Key

The AI sheet scanning feature calls the Anthropic API directly from the browser.  
The app uses the key provided by the Claude.ai hosting environment.  
If you self-host, you will need to proxy the API call server-side to keep your key secure.

## Project Structure

```
noteread/
├── index.html      # Entire app — single file
├── manifest.json   # PWA manifest (name, icons, display mode)
├── sw.js           # Service worker (offline caching)
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

## License

MIT — free to use, modify, and distribute.
