# Ewan's Strength Training

> **When** you're at the gym with your phone and no reliable signal, **you want** your workout plan right there — sets, reps, weights, rest timers — **so you can** train without friction and track progression session to session.

---

## The Problem With Generic Fitness Apps

Most workout apps assume you're on Wi-Fi, have an account, and want to browse content. At the gym, you want none of that. You want:

- Your specific programme, not a library of 5,000 exercises
- No ads breaking your focus mid-set
- No login wall when the gym Wi-Fi drops
- Something that loads instantly from your home screen

This app is a single HTML file. It installs on your phone like a native app, caches everything locally, and works with zero signal.

---

## What Makes It Different

| | Generic Fitness App | This |
|---|---|---|
| **Offline** | Partial or none | Full — service worker caches everything |
| **Install** | App Store / account required | Add to Home Screen from browser |
| **Your programme** | Generic library | Fixed to your actual session |
| **Rest timers** | Sometimes | Per-exercise (120s deadlifts, 90s lunges, 60s push-ups) |
| **Weight tracking** | Separate log screen | Inline per exercise, persists across sessions |
| **Progression cues** | Subscription | Built in — e.g. "progress to 65kg over 8-12 weeks" |
| **Ads / upsell** | Yes | No |

---

## The Session

Four colour-coded sections, collapsible, with per-exercise progress tracking.

**Warmup** (cyan) — ~10 min
- Gentle cardio (3-4 min)
- Mobility: hip circles, arm circles, leg swings
- Dynamic stretching: walking lunges, high knees

**Lower Body** (amber) — ~30 min
- Barbell Deadlifts — 4 × 8-12 @ 50kg → target 65kg
- Reverse Lunges — 4 × 8-12 per leg @ 2×10kg
- Step Ups (Deadleg) — 4 × 8-12 per leg @ 2×10kg · alt: explosive bodyweight

**Upper Body Push** (green) — ~10 min
- Push-ups — 3 × 8-12 · alt: Kettlebell Rows 30kg

**Cooldown** (purple)
- Easy cardio, static stretches (30-60s holds)

**Progression rule**: hit 12 reps → add 2.5kg next session.

---

## Installing as a PWA

On iPhone (Safari):
1. Open the app URL in Safari
2. Tap the Share button → **Add to Home Screen**
3. Tap Add

On Android (Chrome):
1. Open the URL in Chrome
2. Tap the three-dot menu → **Add to Home Screen** (or install banner appears)

Once installed, it opens full-screen with no browser chrome and works completely offline. The service worker pre-caches all assets on first load — including exercise images — so there's no dependency on network after that.

---

## Running Locally

```bash
# Open directly (no PWA install, but everything else works)
open index.html

# Serve for PWA testing (install + service worker require HTTPS or localhost)
python3 -m http.server 8000
# then open http://localhost:8000
```

---

## Tech Stack

- **Single file**: `index.html` — 1,496 lines, zero build step, zero dependencies
- **PWA**: `manifest.json` + `sw.js` — cache-first strategy, versioned (`ewans-exercises-v3`), portrait/standalone
- **Fonts**: Cormorant Garamond (headings) + Outfit (body) via Google Fonts — cached after first load
- **CI**: HTML lint on push

```
ewans-exercises/
  index.html          # The entire app
  manifest.json       # PWA config
  sw.js               # Service worker
  icons/              # icon-192.svg, icon-512.svg
  images/             # deadlift.png, pushup.png, reverse-lunge.png, step-up.png
```

---

## Current State

Personal training app — built for one person's programme. The exercises, weights, and progression targets are specific to that programme, not configurable via UI. Works on iOS and Android. Last updated: 2026-03-08.

---

MIT
