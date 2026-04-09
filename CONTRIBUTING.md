# Contributing to Altitude

Altitude is a flight tracker with a clear design philosophy and a tight scope.

Before contributing, understand what the project is — and what it refuses to be.

---

## Read this first

Altitude is not a community project in the sense of "the more the merrier." The design language, architecture, and philosophy are specific. Contributions that add noise, complexity, or features outside the roadmap won't be merged — regardless of how well they're written.

If you're unsure whether your contribution fits, open a discussion before writing a single line of code. A five-minute conversation saves both of us time.

Bug fixes and documentation improvements can go straight to a PR — no issue needed.

---

## Philosophy

Altitude must remain:

- **Clean** — the surface never accumulates noise for edge-case users
- **Honest** — no dark patterns, no manipulative UI, no undocumented data collection
- **Intentional** — nothing exists by accident
- **Dual-mode** — light and dark are both first-class; every change must look right in both

**Non-negotiable — these will never be added:**
- Advertising or sponsored content of any kind
- Analytics without explicit opt-in
- Features that clutter the main passenger experience
- Anything that removes or weakens the easter eggs — the Kollsman window, the VOR spinner, the orange

If your contribution adds complexity, it must add clarity by a greater margin. That's the bar.

---

## Architecture rules

Follow the established patterns. Do not introduce new ones without prior discussion.

**Core rules:**
- **MVVM strictly** — no business logic in Composables, no UI logic in Repositories
- **StateFlow throughout** — UI reads state, never mutates ViewModel state directly
- **Hilt for DI** — no manual dependency wiring
- **Kotlin only** — no Java files
- **Jetpack Compose only** — no XML layouts

**New dependencies:**
Every new dependency requires justification in the PR description. If the result can be achieved with what's already in the project, that approach wins. Large, proprietary, or privacy-concerning dependencies won't be accepted.

---

## How to contribute

1. **Fork** the repository
2. **Open an issue** if your change is a new feature — confirm it fits before building it
3. **Create a branch** — `fix/what-it-fixes` or `feature/what-it-adds`
4. **Keep changes focused** — one concern per PR. Don't combine a bug fix with a refactor.
5. **Run ktlint** before committing

```bash
./gradlew ktlintCheck
./gradlew ktlintFormat
```

6. **Write tests** — new features need unit tests for the ViewModel and repository layer; bug fixes need a test that would have caught the bug
7. **Open a Pull Request** including:
   - A clear description of what changed and why
   - Screenshots or screen recording for UI changes
   - Confirmation that both light and dark modes look correct

---

## Commit style

Follow [Conventional Commits](https://www.conventionalcommits.org/). Write messages that explain *why*, not just *what*:

```
# Good
fix: delay notification now fires before boarding call, not after

# Not helpful
fix: notifications
```

Prefixes: `feat:` `fix:` `docs:` `refactor:` `test:` `chore:`

---

## Before you submit

Verify every item:

- [ ] Tested on a real device or emulator with API 26+
- [ ] Light mode: nothing broken or misaligned
- [ ] Dark mode: nothing broken or misaligned
- [ ] No business logic introduced into Composables
- [ ] No new dependencies without justification in the PR description
- [ ] No new lint warnings
- [ ] ktlint passes
- [ ] Tests written or updated where applicable
- [ ] Easter eggs untouched

---

## What we're looking for

**High priority:**
- Bug fixes with reproduced test cases
- Performance improvements with measured benchmarks
- Accessibility improvements
- Documentation improvements

**Welcome:**
- New features that fit the V1 roadmap
- UI polish that respects the design system
- Additional unit test coverage

**Unlikely to be merged:**
- Features that belong in V2 without a V1 version to start from
- UI changes that add clutter to the main passenger experience
- Anything that adds tracking, analytics (without opt-in), or ads

---

## Bug reports

Open a GitHub Issue and include:

- Device model and Android version
- Whether it occurs in light mode, dark mode, or both
- Steps to reproduce — specific enough that someone else can follow them
- Expected behaviour vs actual behaviour
- Logcat output if relevant — redact anything personal before pasting

---

## Feature requests

Open a Discussion, not an Issue. Issues are for confirmed bugs and accepted feature work only.

Read the roadmap in the README before opening a feature request. If what you're asking for belongs in V2, note that — it might still be worth discussing.

---

## Questions

Open a Discussion. The project has a clear philosophy and a maintainer who is happy to talk through whether something fits — but not through Issues, which are tracked for actionable work.

---

Altitude is built by people who care about craft.
Contributions should be too.

---

— **waleedahmedja**
