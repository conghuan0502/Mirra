# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

The design surface recorded here is the web landing page (branch `landing-page`). The product itself is a native macOS AppKit app (`src/app/`, Objective-C) with a Python helper runtime (`scripts/`). The app's own interface follows native macOS conventions and is not governed by web design decisions.

## Stack

Landing page: Astro + TypeScript, GSAP for animation, Lenis for smooth scrolling, plain CSS (no utility framework). The landing page is separate from the app build (`make app`, `make package`).

Location: the `landing/` folder at the repo root. Deploy: GitHub (GitHub Pages).

Primary hero button links to the latest DMG release (`github.com/eiyuumiru/Mirra/releases/latest`).

## Users

- **Primary:** an Intel Hackintosh owner on a supported macOS build who wants Apple's iPhone Mirroring and has a separate jailbroken iPhone to use as the bridge. Technically comfortable with SSH, jailbreak tooling (OpenSSH, `ldid`), compatibility tables and log files. Their job is to judge whether their setup qualifies, install the app, complete bridge setup and get a working Mirroring session.
- **Secondary:** testers and contributors who can try other bridge models, iOS versions, jailbreak layouts, macOS builds and Wi-Fi/video drivers, and report results with configuration and logs (see `docs/Roadmap.md`, `CONTRIBUTING.md`).

## Product Purpose

Mirra is a native macOS companion that makes Apple's iPhone Mirroring usable on a Hackintosh. It prepares a separate jailbroken iPhone as a bridge, keeps the bridge connection available in the background, checks the connection before launch and then opens Apple's iPhone Mirroring app, which provides the screen, keyboard, pointer and authentication.

Success: a qualifying user gets from download to a connected Mirroring session through guided setup, and the connection recovers on its own after failures, sleep or login.

## Positioning

Mirra does not reimplement iPhone Mirroring. It adapts macOS software interfaces and delegates selected cryptographic operations to a jailbroken bridge iPhone, so Apple's own app does the mirroring. **The iPhone you mirror does not need a jailbreak**; only the separate bridge does.

## Operating Context

- Host: Intel `x86_64` Hackintosh. Currently accepted: macOS 26.7.2 (`25G332`) with iPhone Mirroring 1.6 (`98.5`). Unsupported host builds are rejected by the compatibility check.
- Requires working AWDL Wi-Fi and H.264 VideoToolbox decoding on the host.
- Bridge: a compatible jailbroken iPhone with OpenSSH and `ldid`, reached over Wi-Fi SSH or USB (`docs/Bridges.md`).
- Target iPhone: meets Apple's iPhone Mirroring requirements; kept locked and nearby with Wi-Fi and Bluetooth on.
- Install: DMG from GitHub Releases, drag to Applications. Python runtime and helpers are bundled.
- Setup flow: SSH fingerprint verification → authorize → **Prepare connection** → **Finish setup** → **Connect**.
- Evaluation rituals: reading the compatibility table, the troubleshooting table and the docs before installing; filing bug reports with configuration and logs.

## Capabilities and Constraints

- Guided bridge setup with verified SSH access and automatic certificate preparation; rootless and RootHide deployment support.
- Background service with recovery after bridge connection failures; starts at login.
- Connection checks before opening iPhone Mirroring.
- Native error dialogs with optional logs; live log viewer, dated log files, seven-day retention, **Open log folder**.
- System, Light and Dark appearance options.
- Current version: 0.1.0. Status: **experimental**.
- Not a full T2 chip replacement and no equivalent hardware security guarantees. May not work even when listed requirements are met; updates may break functionality. Full-resolution video is not guaranteed.
- Uses private macOS interfaces.

Terminology to keep consistent with the app and docs: "bridge" (the jailbroken iPhone), "the iPhone you mirror" / "target iPhone", "background support", "Prepare connection", "Finish setup", "Connect", "Connection help".

## Brand Commitments

- Name: **Mirra**. Tagline in use: "Your iPhone. On your Hackintosh." (the app's home screen reads "Your iPhone. On your Mac.").
- Icon: `docs/images/icon.png`.
- Must state that Mirra is an independent community project, **not affiliated with Apple**, and must carry the experimental status and its limits honestly. Never imply Apple endorsement or guaranteed compatibility.
- Voice (from README and docs): plain, precise, technical and candid about limits; short declarative sentences; UI labels in bold.
- Canonical links: source and releases at `github.com/eiyuumiru/Mirra`; support at `ko-fi.com/eiyuumiru`. This checkout's remote (`conghuan0502/Mirra`) is not the canonical home.
- License: MIT (`LICENSE`); third-party notices in `NOTICE.md`.

## Evidence on Hand

- Screenshots: `docs/images/app-dark.png` (home), `docs/images/settings.png`, `docs/images/setup.png`, `docs/images/mirroring-spotify.png`, `docs/images/mirroring-video.png`.
- Compatibility, troubleshooting and documentation tables in `README.md`; guides in `docs/`.
- Changelog for 0.1.0 in `CHANGELOG.md`.
- **Absent, do not fabricate:** user counts, download numbers, testimonials, press, benchmarks or latency/quality figures, a list of verified bridge models beyond `docs/Bridges.md`, pricing (the app is free and MIT-licensed; Ko-fi is optional support).

## Product Principles

1. **Honest about limits first.** Requirements, experimental status and non-affiliation are part of the product, not fine print. Qualify users early so the wrong ones don't waste an evening.
2. **Apple's app does the mirroring.** Mirra prepares and maintains the bridge; it never claims to provide the screen, input or authentication itself.
3. **Guided, verifiable steps.** Every setup action is explicit and checkable (fingerprints, readiness, logs), never hidden magic.
4. **Diagnosable by default.** Logs, connection checks and recovery instructions are first-class so users and contributors can report precisely.
5. **Invite contribution.** Broader compatibility depends on testers; make it clear what to try and how to report it.

## Accessibility & Inclusion

The app uses native accessibility labels and honors Reduce Motion (`src/app/app.m`). The landing page should match that: respect `prefers-reduced-motion` for GSAP/Lenis effects (including disabling smooth scroll) and keep content fully usable without animation.
