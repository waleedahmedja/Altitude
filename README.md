<div align="center">

<br/>

# A L T I T U D E

**The Android flight tracker built for the passenger who cares.**

[![License](https://img.shields.io/badge/license-MIT-orange.svg?style=flat-square)](LICENSE.md)
[![Platform](https://img.shields.io/badge/platform-Android-green.svg?style=flat-square)](https://android.com)
[![API](https://img.shields.io/badge/API-26%2B-brightgreen.svg?style=flat-square)](https://android-arsenal.com/api?level=26)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.0-blue.svg?style=flat-square)](https://kotlinlang.org)
[![Status](https://img.shields.io/badge/status-In%20Development-orange.svg?style=flat-square)]()


</div>

---

## What is Altitude?

Most flight apps are built for plane spotters. Altitude is built for the person on the plane.

One flight card. Everything you need. Nothing you don't. Gate changes before your airline tells you. A live map that looks like it came from a design studio, not a GPS app. A personal flight log that gets richer every time you fly.

And for those who look closely — a few things that only make sense if you already know.

---

## Features

### For the Passenger
- **Flight Card** — status, gate, terminal, aircraft, boarding time. One glance, you're informed
- **Smart Alerts** — gate changes, delays, boarding calls. Faster than your airline app
- **Live Map** — great circle route, real-time aircraft position, altitude profile strip
- **"Who's Landing?" Mode** — track someone else's arrival. Built for the person waiting at arrivals
- **Cancelled State** — when a flight dies, the app doesn't. See next available flights instantly

### For the Traveller
- **Flight Log** — every flight you've ever tracked, archived and searchable
- **Passport Map** — a personal world map with arc lines for every route you've flown
- **Home Screen Widget** — your next flight's status without opening the app

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Kotlin 2.0 |
| UI | Jetpack Compose |
| Architecture | MVVM + StateFlow |
| DI | Hilt |
| Database | Room |
| Networking | Retrofit + OkHttp |
| Maps | MapLibre Android SDK |
| Widget | Jetpack Glance |
| Background | WorkManager |
| Auth | Firebase Anonymous Auth |

### Data Sources (All Free)
- **OpenSky Network** — live aircraft position, heading, altitude, speed
- **AviationStack** — flight status, schedules, delay information
- **aviationweather.gov** — METAR, TAF, SIGMET, NOTAM
- **MapLibre + OpenStreetMap** — custom styled map tiles
- **wttr.in** — plain language airport weather

---

## Architecture

```
altitude/
├── app/
│   ├── data/
│   │   ├── local/          # Room database, DAOs, entities
│   │   ├── remote/         # Retrofit APIs, DTOs
│   │   └── repository/     # Single source of truth
│   ├── domain/
│   │   ├── model/          # Domain models
│   │   └── usecase/        # Business logic
│   ├── ui/
│   │   ├── theme/          # Colour system, typography, shapes
│   │   ├── onboarding/     # Walkthrough screens
│   │   ├── home/           # Flight list, empty state
│   │   ├── flight/         # Flight card, detail, map
│   │   ├── log/            # Flight history, passport map
│   │   └── settings/       # Preferences, about
│   ├── widget/             # Glance widget — small + medium
│   └── worker/             # Background status polling
```

---

## Getting Started

### Prerequisites
- Android Studio Hedgehog or later
- JDK 17+
- Android SDK API 26+

### Setup

1. Clone the repository
```bash
git clone https://github.com/yourusername/altitude.git
cd altitude
```

2. Create a `local.properties` file in the root directory and add your API keys
```properties
AVIATIONSTACK_API_KEY=your_key_here
```

3. Open in Android Studio and sync Gradle

4. Run on a device or emulator with API 26+

> OpenSky Network, aviationweather.gov, and wttr.in require no API keys.

---

## Design Philosophy

Altitude follows three rules that don't bend.

**One.** The surface is always clean. If a passenger opens this app stressed and running late, they find what they need in under three seconds.

**Two.** Depth is always available. Every screen has a secondary layer for whoever wants it. We never lock things away — we just don't shout about them.

**Three.** Both light and dark modes are designed from scratch. Not one inverted from the other. They are two separate atmospheres that communicate the same truth.

The colour system is deliberate. Red-orange wavelengths preserve night vision — the reason cockpit instruments have glowed this colour since before either of us were born. We use the same colour because this app is built by people who noticed that, and cared.

---

## Roadmap

### V1.0 — Foundation
- [ ] Project setup, architecture, navigation graph
- [ ] Theme system — light + dark, full colour tokens
- [ ] Flight search and add
- [ ] Flight Card — all states
- [ ] Live flight status via AviationStack
- [ ] Smart alerts — 3 tiers
- [ ] Onboarding walkthrough
- [ ] Home screen widget (Glance)
- [ ] Flight log + passport map
- [ ] Settings + Kollsman easter egg

### V1.5 — The Map
- [ ] MapLibre integration with custom styled tiles
- [ ] Great circle route rendering
- [ ] Live aircraft position overlay
- [ ] Altitude profile strip
- [ ] Weather overlay toggle
- [ ] METAR airport detail on tap

### V2.0 — Depth
- [ ] NOTAM awareness
- [ ] Calendar sync
- [ ] Flight sharing
- [ ] Connection assistant
- [ ] Monetisation exploration

---

— **waleedahmedja**
