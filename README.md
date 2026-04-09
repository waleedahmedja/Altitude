<div align="center">

# A L T I T U D E

**Not your average flight tracker.**

Built with Kotlin and Jetpack Compose. Designed for the passenger.

<br/>

[![Kotlin](https://img.shields.io/badge/Kotlin-2.0-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](https://kotlinlang.org)
[![Compose](https://img.shields.io/badge/Jetpack_Compose-latest-4285F4?style=flat-square&logo=jetpackcompose&logoColor=white)](https://developer.android.com/jetpack/compose)
![API](https://img.shields.io/badge/Min_SDK-26-green?style=flat-square)
![License](https://img.shields.io/badge/License-Custom-orange?style=flat-square)
![Status](https://img.shields.io/badge/Status-In_Development-orange?style=flat-square)

<br/>

</div>

---

## The Idea

Most flight apps are built for plane spotters.

Altitude fills a gap that still exists on Android — a flight tracker built for the person actually on the plane. One card. Everything you need. Nothing you don't. Gate changes before your airline tells you. A live map that looks like it came from a design studio, not a GPS app. A personal flight log that gets richer every time you fly.

And for those who look closely — a few things that only make sense if you already know.

---

## What It Does

| Feature | Description |
|---|---|
| **Flight Card** | Status, gate, terminal, aircraft, boarding time. One glance, you're informed |
| **Smart Alerts** | Gate changes, delays, boarding calls. Faster than your airline app |
| **Live Map** | Great circle route, real-time aircraft position, altitude profile strip |
| **"Who's Landing?" Mode** | Track someone else's arrival. Built for the person waiting at arrivals |
| **Cancelled State** | When a flight dies, the app doesn't. See next available flights instantly |
| **Flight Log** | Every flight you've ever tracked, archived and searchable |
| **Passport Map** | A personal world map with arc lines for every route you've flown |
| **Home Screen Widget** | Your next flight's status without opening the app |

---

## What It Doesn't Do

- Ads of any kind
- Dark patterns or manipulative UI
- Data collection beyond what's documented in the Privacy Policy
- Noise for the passenger who just needs to know if their gate changed

---

## Architecture

Altitude follows clean MVVM with unidirectional data flow throughout.

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

**Key principles:**
- UI reads from `StateFlow` — never mutates ViewModel state directly
- MVVM + Hilt throughout — no business logic in Composables
- Flight history lives entirely on-device — no Altitude cloud, no Altitude servers

---

## Built With

| Layer | Choice |
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

### Data Sources (All Free)

| Service | Purpose |
|---|---|
| OpenSky Network | Live aircraft position, heading, altitude, speed |
| AviationStack | Flight status, schedules, delay information |
| aviationweather.gov | METAR, TAF, SIGMET, NOTAM |
| MapLibre + OpenStreetMap | Custom styled map tiles |
| wttr.in | Plain language airport weather |

---

## Getting Started

**Prerequisites:**
- Android Studio Hedgehog or later
- JDK 17+
- Android SDK API 26+

**Clone and run:**

```bash
git clone https://github.com/waleedahmedja/altitude.git
cd altitude
```

Create a `local.properties` file in the root directory:

```properties
AVIATIONSTACK_API_KEY=your_key_here
```

Open in Android Studio. Sync Gradle. Run on a device or emulator with API 26+.

> OpenSky Network, aviationweather.gov, and wttr.in require no API keys.

---

## Design Philosophy

Altitude follows three rules that don't bend.

**One.** The surface is always clean. If a passenger opens this app stressed and running late, they find what they need in under three seconds.

**Two.** Depth is always available. Every screen has a secondary layer for whoever wants it. We never lock things away — we just don't shout about them.

**Three.** Both light and dark modes are designed from scratch. Not one inverted from the other. Two separate atmospheres communicating the same truth.

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
