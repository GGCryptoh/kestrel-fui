# KESTREL · MI6 Mission Profile FUI

> A single-file, browser-based **FUI** (Fictional User Interface) — a Bourne-style MI6 / Treadstone mission-profile dashboard. Drag, resize, glitch, scan. No build step, no dependencies, no backend.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![No Build](https://img.shields.io/badge/build-none-brightgreen)
![Single File](https://img.shields.io/badge/single--file-HTML-orange)

**[▶ Live demo](#)** *(enable GitHub Pages on this repo to populate the link)*

---

## What is this

A "**FUI**" — short for *Fictional User Interface*, also called **screen graphics** or a **playback graphic** in film/TV production — is the pretend-real software you see on a character's monitor. Studios like Territory, Perception NYC, Cantina Creative, and Method specialise in nothing else. *Minority Report. The Bourne films. Mr. Robot. Iron Man. Severance.* All FUI.

`kestrel-fui` is one of those, in your browser, tilted at a Bourne-era SIS/MI6 ops desk. It's a **single HTML file** — open it and you're in the field office.

## Features

| | |
|---|---|
| 🖱 **Draggable, resizable windows** | Like a real ops dashboard — minimize, maximize, close. ESC restores or closes. |
| 📡 **Live track radar** | Topographic wireframe underlay (contour rings, street grid, river/Bosphorus) with a green sweep + animated blips. |
| 👤 **Subject dossier** | Random AI-generated face (`thispersondoesnotexist`, falls back to `picsum`), redacted name, threat chips, glitching codename. |
| 👥 **Associates database** | 5 fixed records — VIPER, MAGPIE, COBALT, WIDOW, OWL. Auto-cycles. ◀ ▶ buttons, clickable thumb strip, **arrow-key** navigation. |
| 🪪 **Aliases ledger** | 7 legend identities with `ACTIVE / BURNED / EXPIRED` status. |
| 🩻 **Biometrics — fingerprints** | Procedurally generated whorl, loop, arch, and partial prints with **minutiae overlays** (ridge endings, bifurcations, core, delta). Click to inspect. |
| 👁 **Iris / retinal scan** | SVG-rendered eyes with sclera veins, iris striations, crypts, Daugman landmarks. Hamming-distance match scores. |
| 📄 **Redacted documents** | Paper-textured dossiers with `█████` block-outs, `CLASSIFIED / EYES ONLY / VOID` rubber stamps. Click thumbs to read. |
| 🗺 **Movement map** + 🎥 **Surveillance** | CCTV / drone / HUMINT / SAT frames with REC dots + click to enlarge. |
| 📡 **SIGINT log + Decrypt stream + Terminal** | Rolling intercept feed, animated AES hex dump, fake `ssh + tail -f` shell. |
| 🧰 **Right widget dock** | Spawn extra props on demand: surveillance album, hit contract, city blueprint, plot threads, ledger fragment, M.E. report. |
| 💾 **localStorage persistence** | Window positions, sizes, spawned panels, scroll position, current associate — all remembered across refreshes. |
| ⌨️ **Keyboard** | `ESC` closes modals → restores maximized → closes spawned. `← / →` cycles associates. |
| 🎚 **Constant ambient motion** | CRT scanlines, flicker, marquee, sweeping radar, pulsing blips, ticking telemetry, glitch bars on CCTV, animated waveform, code stream. |

## Quick start

```bash
git clone https://github.com/<your-handle>/kestrel-fui
cd kestrel-fui
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

That's it. No `npm install`. No build step. No backend.

## Embedding it on a real prop monitor

Producers or DPs wanting to use it as on-set playback:

1. Run a tiny static server so timestamps tick from the host clock (e.g. `python3 -m http.server`), or just open the file directly in fullscreen.
2. Hide cursor with `cursor: none;` on `body` if you're filming the screen.
3. Adjust the `--bg` and `--amber` CSS variables at the top of the file to match your colour palette / DOP request.
4. Replace external images (`picsum.photos`, `thispersondoesnotexist.com`, `pravatar.cc`) with cleared, on-disk stills if your set is offline.

## Customising the dossier

Almost everything is data-driven near the bottom of `index.html`. Search for these constants:

| Const | What it controls |
|---|---|
| `ALIASES`     | Legend identities + status |
| `ASSOCIATES`  | Cycling network of accomplices |
| `FPS`         | Fingerprints (hand, type, match score) |
| `EYES`        | Iris records |
| `DOCS`        | Redacted documents |
| `SPAWN_DEFS`  | Right-dock spawnable windows |
| `briefText`   | The typewriter brief |
| `seeds`       | The SIGINT intercept feed |
| `cmds`        | The shell/terminal lines |

Replace the strings, change the photos, ship a different episode.

## Tech notes

- Single HTML file. Vanilla CSS + JS. No frameworks, no bundler, no transpiler.
- Fonts: `JetBrains Mono`, `VT323`, `Special Elite` — loaded from Google Fonts.
- Images: `picsum.photos`, `thispersondoesnotexist.com` (with `picsum` fallback), `pravatar.cc`.
- The fingerprint and iris graphics are SVG generated procedurally from a deterministic PRNG (`mulberry32`-style).
- Storage key: `mi6.dashboard.v2` in `localStorage`. Use the ⟲ button on the right dock to clear and reset.
- Browser support: any evergreen Chromium / Firefox / Safari.

## Inspirations / further reading

- [Territory Studio](https://www.territorystudio.com/) — *Blade Runner 2049, Mission Impossible: Fallout, The Martian.*
- [Perception NYC](https://experienceperception.com/) — *Black Panther, Iron Man.*
- [Cantina Creative](https://www.cantinacreative.com/) — *Captain America, Avengers.*
- [Hudson + Hudson Hawk](https://www.hudsonhawk.com/) — *Mr. Robot.*
- Mark Coleran ([coleran.com](https://coleran.com/)) — coined "FUI." His reels are the canonical reference.
- The book [*Make It So: Interaction Design Lessons from Sci-Fi*](https://rosenfeldmedia.com/books/make-it-so/) by Shedroff & Noessel.

## License

MIT — see [LICENSE](LICENSE). Use it for student films, indie shows, ARGs, teaching, portfolio pieces. If you ship it on something with a real audience, a credit is appreciated but not required.

---

Built by [Geoff Hopkins](https://www.linkedin.com/in/geoffhopkins/) with `claude-code`. Pull requests welcome — extra panels, new associate records, better fingerprints.
