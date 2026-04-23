# CarID — Car Identifier

A zero-install, mobile-first web app that identifies any car you point your camera at, using Claude's Vision API and your device's GPS.

## How it works

1. Enter your Anthropic API key (stays in your browser, never stored server-side)
2. Point your camera at a car (or upload a photo)
3. Get instant identification: brand, model, year, confidence score, and tags
4. See the GPS coordinates captured at the moment of the shot

## Features

- **Live camera** with rear-facing preference and a viewfinder overlay
- **GPS tagging** — latitude, longitude, altitude, and accuracy stamped on every result
- **Claude Vision** — powered by `claude-opus-4-5` via the Anthropic Messages API
- **File upload fallback** for devices that block camera access
- **Pure HTML/CSS/JS** — no build step, no dependencies, works offline after first load
- **API key privacy** — key lives only in memory for the session; never sent anywhere except `api.anthropic.com`

## Usage

Open `index.html` directly in a browser, or serve it from any static host (GitHub Pages, Netlify, Vercel, etc.).

```
# Serve locally
npx serve .
# or
python3 -m http.server 8080
```

Then visit `http://localhost:8080` and enter your [Anthropic API key](https://console.anthropic.com).

## Requirements

- A modern browser with camera and geolocation support (Chrome/Safari on iOS/Android works great)
- An Anthropic API key with access to `claude-opus-4-5`

## Stack

| Layer | Technology |
|---|---|
| UI | Vanilla HTML + CSS (Syne + DM Mono fonts) |
| Vision AI | Anthropic Claude Vision API |
| Location | Web Geolocation API |
| Camera | MediaDevices / getUserMedia |
| Hosting | Any static file server |

## Privacy

Your API key and photos never leave your device except for the direct call to `api.anthropic.com`. No backend, no analytics, no storage.
