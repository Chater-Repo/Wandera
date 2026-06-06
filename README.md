<div align="center">

# ✈️ Wandera

**A polished, local-first travel planner for Windows & Android**

Plan every detail of your trips — flights, hotels, transport, activities, documents and more — in one organised place. No accounts, no cloud, no analytics. All your data stays on your devices.

[![Latest release](https://img.shields.io/github/v/release/Chater-Repo/Wandera?display_name=tag&color=3b82f6)](https://github.com/Chater-Repo/Wandera/releases/latest)
[![Built with Tauri](https://img.shields.io/badge/built%20with-Tauri%202-24c8db)](https://tauri.app)
[![React](https://img.shields.io/badge/React-18-61dafb)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178c6)](https://www.typescriptlang.org)

</div>

---

## Why Wandera?

Most travel apps either lock your data behind a subscription, ship it to a third party, or feel like glorified spreadsheets. Wandera is a cross-platform app that organises every aspect of a trip in one place — and your data never leaves your devices unless you explicitly export it.

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

### 💸 Daily expense tracker
- Dedicated expense tracker per trip — tap **Track Expenses** from the trip detail page
- Log expenses by day and category: Food & Drink, Transport, Accommodation, Activities, Shopping, Health, Other
- **Lockable exchange rates** — lock the rate at the time of purchase so historical entries don't drift with the market
- Optional location with map pinning — expense pins appear on the trip map alongside hotels, flights and activities
- Payment method per entry — cash, card, or other
- Budget bar showing total spent vs. your spending money target, with over/under status and remaining amount
- Category breakdown chips at the top so you can see at a glance where your money went
- Date-grouped entry list; amounts shown in the local currency with automatic conversion to your home currency

### 💰 Budget tracking
- Per-trip budget with category breakdown bars
- **Spending money** with live destination-currency conversion (multi-country trips show all conversions)
- Over/under budget status with traffic-light colours
- **Total Spent** in the trip hero adds all booked costs (flights, hotels, transport, connectivity, insurance, activities) together with your logged daily expenses — spending money is excluded as it's a budget allocation, not a committed cost

### 🌍 Destination briefing
- **Quick Facts** — currency, plug type, voltage, dialling code, emergency numbers, languages (offline, bundled)
- **Travel Advisory** — live from smartraveller.gov.au
- **Visa Requirements** — based on your passport via passportindex.org

### 🕒 At-a-glance context
- **Auto trip status** — Planning → Upcoming (60 days out) → Active (on start date) → Completed; shown as a badge everywhere without touching your stored data
- Current local time at destination with timezone label
- **Live currency converter** — type any amount in your trip currency and see it instantly in the destination currency; swap direction with one click
- Trip overview paragraph auto-generated from your data
- Countdown badges on the sidebar for upcoming trips

### 🗺️ Map and calendar
- Trip map with coloured markers per category: hotels (amber), airports (blue), train stations (purple), ferry ports (cyan), attractions & expense locations (green)
- **Toggleable map layers** — click any legend item to show or hide that marker type, flight arc, transport route, or ferry route; only types that exist in the trip are shown, so the legend never shows empty categories
- Month-grid calendar plotting flights, hotels, transport, activities and insurance coverage as span bars

### 🔄 Sync over home network
- Sync trips between your PC and Android phone over your home Wi-Fi — no cloud involved
- Pair once by scanning a QR code shown on the desktop; the 256-bit key never leaves your network
- Choose direction each time: push phone → PC, or pull PC → phone
- All traffic is AES-256-GCM encrypted with your paired key — safe even on a shared network

### 📤 Sharing and backup
- **Share Trip** — exports a single trip as a JSON file with fine-grained privacy controls (opt-out of sensitive sections, booking refs, attachments)
- **Import Trip** — load a trip from another Wandera user; gets fresh IDs to avoid collisions
- **Backup & Restore** — full local backup as JSON; restore replaces everything
- **Automatic backup reminders** after 14 days

### ⚠️ Smart warnings
- **Passport expiry** — flags any traveller whose passport expires during or within 12 months of the trip
- **Date range alerts** — warns if any flight, hotel, transport, insurance, or activity falls outside the main trip dates (e.g. insurance that doesn't cover the full trip, or an activity booked on the wrong day)

### 📱 Android home screen widgets
- **Trip Overview widget** — destination, dates, status, countdown and exchange rate with your cover photo as background
- **Expense Dashboard widget** — today's spend, budget progress bar and two recent expenses at a glance
- **Expenses Shortcut widget** — minimal 1×1 quick-launch to the expense tracker for the pinned trip

### 🎨 Polish
- **Dark theme** throughout
- **PDF Export** — printable trip report with cover, summary, and itemised sections
- **Fast date picker** — tap the month/year header to drill out to year-picker → month-picker → days (great for passport expiry dates 10 years out)
- **In-app User Guide** with all of this documented
- **Auto-updater** via signed GitHub Releases (desktop) — one-click install

### 🔒 Privacy & security by design
- **No account, no cloud, no analytics** — fully local
- Data persists in IndexedDB (trips + attachments) + SharedPreferences (Android widgets)
- LAN Sync works exclusively over your local network — your trip data never touches an external server
- Internet only used for: address & airport search (OpenStreetMap), exchange rates (Frankfurter), destination time (TimeAPI.io), travel advisories, visa data, and update checks. **Never sends your trip details anywhere.**
- All network traffic is HTTPS-only in release builds; cleartext is blocked at the OS level via Android Network Security Config

## Installation

### 💾 Windows
Grab the latest installer from the [Releases page](https://github.com/Chater-Repo/Wandera/releases/latest):
- `Wandera_x.x.x_x64-setup.exe` — install once and Wandera will auto-update on subsequent launches

> The installer is signed for update verification but not yet code-signed by a certificate authority, so Windows SmartScreen may show a "Windows protected your PC" warning on first launch. Click "More info" → "Run anyway" to proceed.

