# Privacy Policy

**Effective date:** April 2026
**Last updated:** April 2026

Altitude is a flight tracking app designed for the passenger. This policy explains how information is — and is not — handled.

---

## Short Version

Altitude uses the flight numbers you search to fetch data from aviation providers. That's it. Nothing is sold. Nothing is shared with advertisers. There are no Altitude servers. Everything that isn't sent to a flight data provider stays on your device.

---

## 1. What Altitude collects

**Flight searches**

When you search for or track a flight, Altitude sends the flight number and a timestamp to third-party aviation data providers. These requests contain no personal identifiers — they are functionally anonymous, the same as any browser search.

**Nothing else**

Altitude does not collect:

- Your name or any personal identifier
- Contact information
- Usage analytics or crash reports
- Advertising identifiers
- Location data (V1 does not request location permission)
- Biometric data
- Browsing history

---

## 2. How your data is used

Flight numbers serve one purpose: fetching flight status and position data.

Requests go to the following services, each with their own privacy policy:

| Service | Purpose | Data sent |
|---|---|---|
| OpenSky Network | Live aircraft position | Flight identifier |
| AviationStack | Flight status, schedules | Flight identifier |
| aviationweather.gov | Weather, METAR, NOTAM | Airport code |
| wttr.in | Plain language weather | Airport code |

**Altitude has no backend.** There is no Altitude server receiving, storing, or processing your data. The only outbound network requests are those described above.

---

## 3. Local storage

All personal data is stored locally on your device using Android's standard storage APIs:

- Flights you've added — stored in a local Room database
- Alert preferences — stored in SharedPreferences
- Cached flight data — stored temporarily for poor-connectivity use
- Theme preference — light, dark, or system

Uninstalling the app removes all of this permanently. There is no cloud sync in V1.

---

## 4. Location

Altitude does not request location permissions in V1.

If a future version uses location — for example, to detect when you're at an airport — it will require explicit permission, be used only while the app is open, never be stored beyond the session, and never be shared with third parties.

---

## 5. Notifications

If you grant notification permission, Altitude uses it to send flight status alerts: gate changes, delays, boarding calls, and landing confirmations. Nothing else. No marketing. No analytics on what you dismiss.

---

## 6. Analytics

There are no analytics in V1. If analytics are introduced in a future version, they will be explicitly opt-in, limited to aggregate non-identifying patterns, and clearly documented in an update to this policy. Silent collection will never happen.

---

## 7. Children's privacy

Altitude does not knowingly collect data from anyone. Since no personal data is collected from any user, no special processing applies to users of any age.

---

## 8. Changes

This policy may be updated to reflect new features or legal requirements. The date at the top of this document will reflect any changes. Significant changes will be noted in the app's release notes.

---

## 9. Contact

Questions about this policy can be raised as a GitHub Issue:
[github.com/waleedahmedja/altitude](https://github.com/waleedahmedja/altitude)

---

*Altitude is built on craft and user trust. Your data is yours.*

— **waleedahmedja**
