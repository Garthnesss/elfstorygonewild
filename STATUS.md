# STATUS.md — ElfStory Gone Wild

**Last updated:** 2026-11-15
**Phase:** Phase 1 — Playable Prototype (BUILT, awaiting Garth hand play-check + Pages enable)
**Repo:** Garthnesss/elfstorygonewild (public, created Nov 15, 2026, initial head `498cc646`, README only at creation)
**Source game:** Garthnesss/Elfstory3d (full-3D dungeon crawler, Overhead Tactical + Chase, Oakhaven, Sunken Citadel)

## Verified states — honest labels only

| Item | State |
|---|---|
| Repo exists (Garthnesss/elfstorygonewild) | CONFIRMED by Garth, Nov 15, 2026 |
| Premise / cast / truck / race-shop loop brief | CONFIRMED by Garth, Nov 15, 2026 |
| REA-Results check | DONE Nov 15, 2026 — no matching entry in local mirror (Oct 25, 2026 snapshot, commit `315e420`) |
| PROJECT_TRUTH / ARCHITECTURE / ROADMAP / STATUS / DESIGN_BIBLE | WRITTEN Nov 15, 2026 — not yet committed/pushed unless a later entry here says so |
| v1 prototype (single-file HTML canvas, 3 modes) | BUILT Nov 15, 2026 — `docs/index.html` 38,395 bytes, JS extracted + `node --check` PASS (verified twice, incl. by Muse directly); BUILT NOT TESTED by hand yet |
| RADHAVEN overworld (walk/drive/crush/talk/collect) | BUILT — 1500×1050 town, 5 NPCs with dialogue, 14 crushable cars, drink cans, T to enter truck, arena gate |
| SUPER OFF-ROAD REMIX race (4 trucks, 4 laps, nitro, cash bags, AI) | BUILT — single-screen oval, 16 waypoints, rubber-band AI, mud/ramps, payouts $1000/$700/$450/$250 |
| VIXEN'S SPEED SHOP (Nitro/Tires/Shocks/Accel/Top Speed) | BUILT — $100/$400/$600/$800/$1000, max 5 levels (nitro max 99), localStorage persistence |
| Freestyle arena mode | PLANNED — Phase 3, not in v1 gate |
| Full Elfstory3d TS/Three.js port | NOT STARTED — Phase 2 |
| Monster Jam modes (Pit Party / Bracket / 2-Wheel / Freestyle) | NOT STARTED — Phase 3 |
| GitHub Pages live | NOT STARTED — Phase 4 |
| Hand play-check by Garth | NOT DONE — owed, final gate |

## Right now

- Docs pack written Nov 15, 2026 (this file + PROJECT_TRUTH.md, ARCHITECTURE.md, ROADMAP.md, DESIGN_BIBLE.md + README.md).
- v1 prototype BUILT Nov 15, 2026: single-file HTML canvas game with 3 modes — (1) RADHAVEN overworld hub, (2) SUPER OFF-ROAD REMIX race, (3) VIXEN'S SPEED SHOP between races. Syntax-verified, not yet hand-played — Garth's play-check is the gate.

## Session log

- **2026-11-15** — Garth created Garthnesss/elfstorygonewild and briefed the full remix: EXTREME premise, hero title, adult female cast of 5, drivable monster trucks, Super Off Road game-within-a-game. REA-Results local mirror checked — no matching entry. Docs pack written. Prototype build started in parallel.
- **2026-11-15 (later)** — Prototype landed: `docs/index.html` 38,395 bytes, identical copy delivered to Garth as `elfstorygonewild.html`; JS `node --check` PASS re-verified by Muse. Monster Jam + Super Off Road research folded into DESIGN_BIBLE.md (original arcade shop prices cited from arcade-museum.com).
- **2026-11-15 (night)** — PUBLISHED to GitHub: first push attempt's approval card timed out unseen (verified not landed); retry approved by Garth and landed as commit `f3d6b5f7` on `main` (7 files: README, 4 canonical docs, DESIGN_BIBLE, docs/index.html) — remote read-back verified despite a 503 in the push response. GitHub Pages not yet enabled (Phase 4).

## Blocked on Garth

- Phase 0 gate: read DESIGN_BIBLE.md, confirm tone/cast/trucks are right.
- Phase 4 gate (later): hand play-check on a real device.

## Known risks / open questions

- Parody-brand line must stay clean: VOLTAGE DEW / CRIMSON BULL / BEAST ENERGY only, never imply real sponsorship.
- Prototype loop must prove fun before Phase 2 port spend — if the race/shop loop doesn't slap in 2D, it won't in 3D.
- Truck upgrade save schema for the 3D port is undecided (Phase 2).
