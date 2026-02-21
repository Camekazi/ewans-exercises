# Ewan's Strength Training

A progressive web app for structured strength training sessions. Installs on your phone, works offline at the gym.

## What It Does

A workout tracker with colour-coded sections (warmup, lower body, upper body, cooldown), exercise illustrations, and a clean amber/cream design. Built as a single HTML file with no dependencies.

## Features

| Feature | How |
|---------|-----|
| **PWA** | Installable on iOS/Android, standalone mode |
| **Offline** | Service worker caches everything — works with no signal |
| **Sections** | Warmup (cyan), Lower (amber), Upper (green), Cooldown (purple) |
| **Exercise images** | Deadlift, pushup, reverse lunge, step up |
| **Animations** | Breathe, float, slide-up, pulse effects |
| **iOS safe area** | Proper viewport-fit for notched devices |

## Tech Stack

- **Framework**: Vanilla HTML/CSS/JavaScript — zero dependencies
- **Fonts**: Cormorant Garamond + Outfit (Google Fonts)
- **PWA**: Service worker with cache-first strategy, versioned cache (`ewans-exercises-v3`)
- **CI**: HTML lint workflow
- **Lines**: 1,496 (single `index.html`)

## Running

```bash
# Just open it
open index.html

# Or serve it for PWA install testing
python3 -m http.server 8000
```

## Project Structure

```
ewans-exercises/
  index.html        # The entire app
  manifest.json     # PWA manifest (portrait, standalone)
  sw.js             # Service worker (cache-first)
  icons/
    icon-192.svg
    icon-512.svg
  images/
    deadlift.png
    pushup.png
    reverse-lunge.png
    step-up.png
```

## License

MIT
