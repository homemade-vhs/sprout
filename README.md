# 🌱 Sprout — Plant Growing Tracker

A single-file web app for tracking indoor and balcony container gardens. Built with vanilla JavaScript, no frameworks, no build step.

## Features

- Track plants from seed through harvest
- Stage progression: germinating → seedling → transplanted → flowering → harvesting → done
- Watering log with reminders
- 80-cell seed tray visualization
- Variety reference database (15 starter varieties)
- Photo attachments (compressed, stored locally)
- Export/import data as JSON
- Works offline — all data in localStorage
- Installable as a PWA

## Architecture

- **Single file**: Everything lives in `index.html` (HTML + CSS + JS)
- **No dependencies**: No frameworks, no CDNs, no external fonts
- **localStorage**: All state persisted under the key `sprout_data`
- **Dark theme**: Default and only theme

## Design Decisions

- **Individual plant records**: Each physical plant gets its own record. When planting multiples, N records are created with auto-incremented locations. This gives per-plant watering logs, notes, and stage tracking at the cost of more records. For a home garden (< 200 plants) this is fine.
- **Base64 photos**: Photos are compressed client-side to ~500KB and stored as base64 data URLs in localStorage. This keeps the app fully offline but limits total photo storage to ~5MB depending on the browser.
- **Variety database**: Hardcoded in JS as a starter set. Users can't add varieties through the UI (yet) but can easily edit the source.

## Live

**https://homemade-vhs.github.io/sprout/**

## Tech

Vanilla HTML/CSS/JS · ES2022+ · localStorage · Service Worker · PWA
