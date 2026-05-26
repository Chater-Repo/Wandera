<div align="center">

# ✈️ Wandera

**A polished, local-first travel planner for Windows**

Plan every detail of your trips — flights, hotels, transport, activities, documents and more — in one organised place. No accounts, no cloud sync, no analytics. All your data stays on your computer.

[![Latest release](https://img.shields.io/github/v/release/Chater-Repo/Wandera?display_name=tag&color=3b82f6)](https://github.com/Chater-Repo/Wandera/releases/latest)
[![Built with Tauri](https://img.shields.io/badge/built%20with-Tauri%202-24c8db)](https://tauri.app)
[![React](https://img.shields.io/badge/React-18-61dafb)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178c6)](https://www.typescriptlang.org)

</div>

---

## Why Wandera?

Most travel apps either lock your data behind a subscription, ship it to a third party, or feel like glorified spreadsheets. Wandera is a desktop app that organises every aspect of a trip in one place — and your data never leaves your computer unless you explicitly export it.

It's designed for people who **actually plan trips** rather than wing them: the sort of traveller who wants their flight times, hotel confirmations, eSIM activation, insurance policies and itinerary all in one window, ideally with their budget tracked alongside.

## Features

### 📋 Trip planning, end to end
- **Flights** — outbound / return columns, multi-leg bookings with a single price for return tickets, timezone-aware durations, `+1d` badges for next-day arrivals, optional ticket attachments
- **Hotels** — check-in/out dates, room type, total cost, address auto-search with map pinning, booking confirmation attachments
- **Other Transport** — trains, buses, ferries, metros, taxis, car rentals with from/to mapping and durations
- **Connectivity** — eSIMs, physical SIMs, roaming and pocket Wi-Fi, with quantity for multi-traveller purchases
- **Insurance** — provider, coverage amounts, emergency contacts, policy attachments
- **Activities** — tours, museums, shows, food and outdoor experiences with location pinning
- **Documents** — passports, visas, tickets and certificates with expiry tracking and in-app PDF/image preview

### 💰 Budget tracking
- Per-trip budget with category breakdown bars
- **Spending money** with live destination-currency conversion (multi-country trips show all conversions)
- Over/under budget status with traffic-light colours
- Counts every category — flights, hotels, transport, connectivity, insurance, activities and spending money

### 🌍 Destination briefing (in one tabbed section)
- **Quick Facts** — currency, plug type, voltage, dialling code, emergency numbers, languages (offline, bundled)
- **Travel Advisory** — live from smartraveller.gov.au
- **Visa Requirements** — based on your passport via passportindex.org

### 🕒 At-a-glance context
- Current local time at destination with timezone label
- **Live currency converter** — type any amount in your trip currency and see it instantly in the destination currency; swap direction with one click
- Trip overview paragraph auto-generated from your data
- Countdown badges on the sidebar for upcoming trips

### 🗺️ Map and calendar
- Trip map with coloured markers per category (hotels, airports, stations, activities)
- Month-grid calendar plotting flights, hotels, transport, activities and insurance coverage

### 📤 Sharing and backup
- **Share Trip** — exports a single trip as a JSON file with fine-grained privacy controls (opt-out of sensitive sections, booking refs, attachments)
- **Import Trip** — load a trip from another Wandera user; gets fresh IDs to avoid collisions
- **Backup & Restore** — full local backup as JSON; restore replaces everything
- **Automatic backup reminders** after 14 days

### ⚠️ Smart warnings
- **Passport expiry** — flags any traveller whose passport expires during or within 12 months of the trip
- **Date range alerts** — warns if any flight, hotel, transport, insurance, or activity falls outside the main trip dates (e.g. insurance that doesn't cover the full trip, or an activity booked on the wrong day)

### 🎨 Polish
- **Light and Dark themes**
- **PDF Export** — printable trip report with cover, summary, and itemised sections
- **Fast date picker** — tap the month/year header to drill out to year-picker → month-picker → days (great for passport expiry dates 10 years out)
- **In-app User Guide** with all of this documented
- **Auto-updater** via signed GitHub Releases — one-click install

### 🔒 Privacy by design
- **No account, no cloud sync, no analytics** — fully local
- Data persists in IndexedDB (gigabytes of capacity, including attachments)
- Internet only used for: address & airport search (OpenStreetMap), exchange rates (Frankfurter), destination time (TimeAPI.io), travel advisories, visa data, and update checks. **Never sends your trip details anywhere.**

## Installation

### 💾 Download (Windows)
Grab the latest installer from the [Releases page](https://github.com/Chater-Repo/Wandera/releases/latest):
- `Wandera_x.x.x_x64-setup.exe` — install once and Wandera will auto-update on subsequent launches

> The installer is signed for update verification but not yet code-signed by a certificate authority, so Windows SmartScreen may show a "Windows protected your PC" warning on first launch. Click "More info" → "Run anyway" to proceed.

### 🛠️ Build from source

Requires:
- [Node.js](https://nodejs.org) 18+
- [Rust](https://rustup.rs) (latest stable)
- [Visual Studio C++ Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/) (Windows)

```bash
git clone https://github.com/Chater-Repo/Wandera.git
cd Wandera
npm install
npm run tauri dev     # development mode with hot reload
# or
npm run tauri build   # production build → src-tauri/target/release/bundle/
```

## Tech Stack

| Layer | Technology |
|---|---|
| Desktop shell | [Tauri 2](https://tauri.app) — small, secure, native Rust + WebView |
| UI framework | [React 18](https://react.dev) + [TypeScript](https://www.typescriptlang.org) |
| Build tool | [Vite](https://vitejs.dev) |
| Icons | [Lucide](https://lucide.dev) |
| Map | [Leaflet](https://leafletjs.com) + OpenStreetMap tiles |
| Storage | IndexedDB (trips + attachments) + localStorage (settings) |
| Routing | [React Router](https://reactrouter.com) |

## External services used (all read-only, no account required)
- [OpenStreetMap Nominatim](https://nominatim.org) — address and airport search
- [Frankfurter](https://www.frankfurter.app) — daily exchange rates (ECB, ~33 major currencies)
- [ExchangeRate-API](https://www.exchangerate-api.com) — fallback exchange rates for currencies not covered by Frankfurter (e.g. TWD, MOP)
- [TimeAPI.io](https://timeapi.io) — IANA timezone lookup by coordinates
- [smartraveller.gov.au](https://www.smartraveller.gov.au) — Australian travel advisories
- [passport-index-dataset](https://github.com/ilyankou/passport-index-dataset) — open-source visa requirements
- [GitHub Releases](https://github.com/Chater-Repo/Wandera/releases) — update manifest and binaries

Each request fetches public data only. No trip information ever leaves your machine.

## Roadmap

A few ideas being considered for future versions:
- Day-by-day itinerary view
- Pre-trip checklist (passport validity, visa applied, vaccinations, etc.)
- Packing list with templates
- Weather forecast for destination
- Trip journal / photos
- Android app (via Tauri Mobile)
- Code signing certificate to remove SmartScreen warnings

## Support Wandera

Wandera is and always will be free. If you've found it useful and want to chip in towards development time, hosting costs, or just a cup of coffee, there's a 💜 **Sponsor** button at the top of this repo, or:

- [Buy me a coffee ☕](https://www.buymeacoffee.com/stevechater) *(replace once signed up)*
- [GitHub Sponsors](https://github.com/sponsors/Chater-Repo)

Every little bit helps keep the project going. Thank you! 🙏

## Contributing

Issues and feature requests are welcome — open one [here](https://github.com/Chater-Repo/Wandera/issues).

If you spot a bug, please include:
- Wandera version (Settings → About)
- Windows version
- Steps to reproduce
- A backup file (Settings → Backup) if the issue involves specific data

## License

Copyright © 2026 Steven Chater. All Rights Reserved.

This software and its source code are the exclusive property of Steven Chater.
No part of this software may be copied, modified, merged, published, distributed,
sublicensed, or sold without the express prior written permission of the copyright owner.

---

<div align="center">

Built for travel — by a traveller. ✈️🌍

</div>
