# Ewan's Strength Training

Offline PWA workout tracker for a specific strength programme — installs from Safari, works with zero signal.

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Open on iPhone → Share → Add to Home Screen → full-screen, offline, no browser chrome.

---

## Install as PWA

**iPhone (Safari):** Open the URL → Share → Add to Home Screen → Add.

**Android (Chrome):** Open the URL → three-dot menu → Add to Home Screen.

The service worker pre-caches all assets including exercise images on first load. No network needed after that.

## The Session

Four colour-coded sections, collapsible, with per-exercise weight tracking.

| Section | Colour | Duration |
|---------|--------|----------|
| Warmup | Cyan | ~10 min |
| Lower Body | Amber | ~30 min |
| Upper Body Push | Green | ~10 min |
| Cooldown | Purple | — |

**Progression rule:** Hit 12 reps → add 2.5kg next session.

## Weight Tracking

Tap any exercise to log your working weight. Numbers persist across sessions in LocalStorage.

## Rest Timers

Each exercise has a built-in rest timer: 120s for deadlifts, 90s for lunges, 60s for push-ups.

---

## Stack

- Single file: `index.html` — 1,496 lines, zero build step, zero dependencies
- Service worker: cache-first, versioned (`ewans-exercises-v3`)
- Fonts cached after first load (Cormorant Garamond + Outfit via Google Fonts)

**Note:** Exercises, weights, and targets are hardcoded for one programme. No UI to configure them.

MIT
