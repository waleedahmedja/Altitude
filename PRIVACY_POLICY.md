# Privacy Policy

**Altitude — Live Flight Tracker**

*Last updated: April 2026*

---

We built Altitude because we care about getting things right. That extends to your data.

This policy is written to be read — not buried. No legalese walls, no buried opt-outs. If something isn't clear, open an issue and we'll fix the language.

---

## The Short Version

- We don't require an account
- We don't sell your data
- We don't run ads
- The only data that leaves your device is what's needed to fetch flight information
- Your flight history lives on your device

That's the honest summary. The full detail follows.

---

## What We Collect

### What We Don't Collect
- Your name
- Your email address
- Your phone number
- Payment information
- Device identifiers tied to you personally

### What the App Uses Locally (Stays on Your Device)
- **Flights you add** — stored in a local Room database on your device only
- **Your alert preferences** — stored in local SharedPreferences
- **Cached flight data** — stored temporarily so the app works with poor connectivity
- **App theme preference** — light, dark, or system

### What Leaves Your Device (To Fetch Flight Data)
When you search for or track a flight, the app makes requests to third-party aviation data providers. These requests contain:
- The flight number or route you searched
- A timestamp

These requests do not contain your identity. They are functionally anonymous — the same request any browser makes when you search for flight information.

**Third-party services we use:**
- [OpenSky Network](https://opensky-network.org/about/privacy) — live aircraft position data
- [AviationStack](https://aviationstack.com/privacy) — flight status and schedule data
- [aviationweather.gov](https://www.weather.gov/privacy) — weather and NOTAM data
- [wttr.in](https://wttr.in/:help) — plain language weather

Each of these services has its own privacy policy, linked above. We encourage you to read them.

### Anonymous Analytics (Optional, Future)
If we introduce analytics in a future version, it will be:
- Explicitly opt-in
- Limited to aggregate, non-identifying usage patterns (e.g. "how many users tap the weather overlay")
- Clearly documented in an update to this policy

We will never collect analytics silently.

---

## Location Data

Altitude does **not** request location permissions in V1.

If a future version uses location (for example, to detect when you're at an airport), it will:
- Require explicit permission granted by you
- Be used only while the app is open
- Never be stored beyond the session
- Never be shared with third parties

---

## Notifications

If you grant notification permission, Altitude uses it to send flight status alerts — gate changes, delays, boarding calls, and landing confirmations.

We don't use notification access for anything else. We don't send marketing notifications. We don't analyse what alerts you dismiss.

---

## Data Storage and Security

All your personal data — flights, preferences, history — is stored locally on your device using Android's standard storage APIs. It is subject to your device's existing security (screen lock, encryption, etc.).

We don't operate servers that store your personal data. There is no Altitude account. There is no Altitude cloud sync in V1.

---

## Children's Privacy

Altitude is not directed at children under 13. We don't knowingly collect information from children. If you believe a child has provided information through the app, please contact us and we will address it promptly.

---

## Changes to This Policy

If we make meaningful changes to this policy, we will:
- Update the "Last updated" date at the top
- Post a clear summary of what changed in the app's release notes
- Not retroactively apply new data practices to data collected under the old policy

Continuing to use the app after a policy update constitutes acceptance of the revised policy.

---

## Contact

Questions, concerns, or just want to tell us something's unclear?

Open an issue on GitHub or reach out directly:
[github.com/waleedahmedja/altitude](https://github.com/waleedahmedja/altitude)

---

*We're independent developers, not a corporation with a legal team. This policy reflects how we actually operate — not how we wish we could get away with operating.*

— **waleedahmedja**
