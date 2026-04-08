# Contributing to Altitude

First — thank you. Altitude is built on the belief that good software is made by people who genuinely care. If you're here, you probably do.

This document tells you how to contribute effectively. Read it once before opening your first PR. It'll save both of us time.

---

## Before You Start

### Check What's Already There
Before building a feature or fixing a bug, search open issues and PRs. Someone might already be working on it. Duplicate effort is nobody's favourite thing.

### Open an Issue First (for New Features)
If you want to add something significant, open an issue and describe what you're thinking before writing code. This lets us discuss the approach, confirm it fits the project's direction, and make sure your time is well spent.

Bug fixes and documentation improvements can go straight to a PR — no issue needed.

---

## The Project's Design Philosophy

Altitude has a point of view. Contributions that fit it will be welcomed. Contributions that fight it will be declined — respectfully, with an explanation.

**The core rules:**

- **Surface is always clean.** Features that add noise to the main UI for edge-case users don't belong in the default experience. Find the right depth for your addition.
- **Both light and dark modes are first-class.** Every UI change must look intentional in both modes. Test both before submitting.
- **Free, no ads, no dark patterns.** We won't accept contributions that introduce advertising, manipulative UI, or data collection beyond what's documented in the Privacy Policy.
- **The easter eggs are sacred.** The Kollsman window, the VOR spinner, the orange — these details have meaning. Don't remove them. Don't make them louder.

If you're unsure whether your contribution fits, ask in an issue first. There are no wrong questions.

---

## Development Setup

### Requirements
- Android Studio Hedgehog or later
- JDK 17+
- Android SDK API 26+
- A device or emulator for testing

### Getting the Code
```bash
git clone https://github.com/yourusername/altitude.git
cd altitude
```

### API Keys
Create `local.properties` in the root directory:
```properties
AVIATIONSTACK_API_KEY=your_key_here
```

OpenSky Network, aviationweather.gov, and wttr.in require no keys.

### Running the App
Open in Android Studio, sync Gradle, and run on a device or emulator with API 26+.

---

## Making a Contribution

### 1. Fork and Branch
```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/what-youre-fixing
```

Use descriptive branch names. `fix/boarding-notification-timing` is better than `fix/bug`.

### 2. Write Your Code

Follow the existing architecture: **MVVM + StateFlow + Hilt**. New features belong in the appropriate layer. Don't put business logic in a Composable. Don't put UI logic in a Repository.

Code style: the project follows standard Kotlin conventions. Run `ktlint` before committing.

```bash
./gradlew ktlintCheck
./gradlew ktlintFormat
```

### 3. Write or Update Tests
- New features should include unit tests for the ViewModel and repository layer
- Bug fixes should include a test that would have caught the bug
- UI tests are welcomed but not required for every change

```bash
./gradlew test
./gradlew connectedAndroidTest
```

### 4. Test Both Modes
Open the app in light mode. Open the app in dark mode. Make sure your change looks right in both. Screenshots in the PR help.

### 5. Commit With Intent
Write commit messages that explain *why*, not just *what*:

```
# Good
fix: delay notification now fires before boarding call, not after

# Not helpful
fix: notifications
```

We follow [Conventional Commits](https://www.conventionalcommits.org/):
- `feat:` — new feature
- `fix:` — bug fix
- `docs:` — documentation changes
- `refactor:` — code restructuring without behaviour change
- `test:` — adding or updating tests
- `chore:` — dependency updates, config changes

### 6. Open a Pull Request

When your PR is ready:
- Fill in the PR template completely
- Link the related issue if there is one
- Include screenshots or a screen recording for UI changes
- Mark it as a Draft if it's not ready for review

---

## PR Review Process

We review PRs with care, not speed. A thorough review is more valuable than a fast one.

What we look for:
- Does it fit the project's philosophy?
- Is the code clean and maintainable?
- Are edge cases handled?
- Does it work in both light and dark modes?
- Does it break anything?

We'll give honest feedback. If we request changes, it's not rejection — it's collaboration.

If a PR isn't going to be merged, we'll say so clearly and explain why. We won't leave contributions hanging.

---

## What We're Looking For

### High Priority
- Bug fixes with reproduced test cases
- Performance improvements with measured benchmarks
- Accessibility improvements
- Documentation improvements

### Welcome
- New features that fit the V1 roadmap (see README)
- UI polish that respects the design system
- Additional unit test coverage
- Kotlin/Compose best practice improvements

### Unlikely to Be Merged
- Features that belong in V2 without a V1 version to start from
- UI changes that add clutter to the main passenger experience
- Dependencies that are large, proprietary, or privacy-concerning
- Anything that adds tracking, analytics (without opt-in), or ads

---

## Questions

Something unclear? Open a GitHub Discussion or tag the maintainers in an issue.

We appreciate everyone who takes the time to contribute — whether it's a one-line fix or a full feature. It all matters.

---

*Altitude is a project built by people who care about craft. We hope that shows, and we hope you'll add to it.*

— waleedahmedja
