# ROADMAP.md — ElfStory Gone Wild

Phases are gated on verification. A phase is DONE only when its gate is checked by a real play session — not when the code merely exists. BUILT NOT TESTED does not pass a gate.

---

## Phase 0 — Extreme Reskin + Bible
**Goal:** Tone, canon, and docs locked before code spreads.

- [x] Repo created: Garthnesss/elfstorygonewild, public, Nov 15, 2026, initial head `498cc646`
- [ ] PROJECT_TRUTH.md / ARCHITECTURE.md / ROADMAP.md / STATUS.md in repo root
- [ ] DESIGN_BIBLE.md: tone guide, slang dictionary, character sheets, truck roster, retheme map, economy tables
- [ ] REA-Results check recorded (done Nov 15, 2026 — no matching entry in local mirror, Oct 25, 2026 snapshot, commit `315e420`)
- [ ] Tone pass: every player-facing string in the prototype plan uses extreme voice + parody brands only (VOLTAGE DEW / CRIMSON BULL / BEAST ENERGY)

**Gate:** Garth reads the Bible and confirms "that's the game." No Phase 1 merge on vibes alone if the tone is wrong.

---

## Phase 1 — Playable Prototype
**Goal:** The full loop, playable end to end, in a single-file HTML canvas game.

- [ ] Mode 1 — RADHAVEN: walk, talk to all 5 NPCs, enter/drive monster truck, crush cars for cash, collect energy drink cans
- [ ] Mode 2 — SUPER OFF-ROAD REMIX: top-down single-screen race, 4 trucks, 4 laps, nitro pickups, cash bags, 3 AI rivals, prize money by finish place
- [ ] Mode 3 — VIXEN'S SPEED SHOP: between races, buy Nitro / Tires / Shocks / Acceleration / Top Speed (5 categories, non-nitro max 5 levels, prices scaled down from arcade originals)
- [ ] Loop closure: shop upgrades visibly change the next race (turning, bounce, accel, top speed, nitro count)
- [ ] Hero + cast present by name: Garth "Mega Ultra Super Huge Dick" Elfstrom, Roxy Rampage, Vixen Voltage, Cherry Bomb, Dixie Dewdrop, Mama Max

**Gate:** One uninterrupted session: RADHAVEN → race → shop → race, with upgraded truck feeling different in race 2. Played by Muse in-browser/headless AND handed to Garth.

---

## Phase 2 — Full Elfstory3d Port
**Goal:** The real game, not just the prototype.

- [ ] Port Elfstory3d TS/Three.js codebase into this repo (Overhead Tactical + Chase preserved)
- [ ] Retheme all zones per DESIGN_BIBLE map (Oakhaven → RADHAVEN, Sunken Citadel → THE SUNKEN STADIUM, etc.)
- [ ] Retheme / rewrite NPCs, quests, dialogue, items in extreme voice
- [ ] Drivable monster truck integrated into the 3D overworld (not prototype-only)
- [ ] Race + Shop loop integrated with 3D game state and saves
- [ ] Existing Elfstory3d test suite carried over and green, plus new tests for truck/race/shop

**Gate:** Full 3D build plays the rethemed campaign path with truck + race loop intact; test suite green; live Pages preview verified by byte/hash check, Elfstory3d-style.

---

## Phase 3 — Monster Jam Modes
**Goal:** The full show, Monster Jam structure.

- [ ] Pit Party — pre-show hub event, hosted by Dixie Dewdrop
- [ ] Bracket Racing — head-to-head single-elimination
- [ ] 2-Wheel Skills — wheelies / stoppies / bicycles, scored
- [ ] Freestyle — big air, backflips, donuts, wheelies, car crushing; timed runs; fan judging
- [ ] Championship arc — Mama Max as reigning champion to dethrone
- [ ] Announcer system — Cherry Bomb calls events live

**Gate:** A full "show" runs in order — Pit Party → Bracket Racing → 2-Wheel Skills → Freestyle → champion crowned — in one session, scored end to end.

---

## Phase 4 — Polish / Pages
**Goal:** Public, playable anywhere, hand-checked.

- [ ] GitHub Pages live for Garthnesss/elfstorygonewild and live-verified
- [ ] Phone controls (touch drive / race / shop) + phone-mode load check
- [ ] Performance + save-compat pass
- [ ] Final tone pass over every string
- [ ] **Hand play-check by Garth** — the final gate, his call only

**Gate:** Garth plays it on his own device and says it slaps. Nothing ships as "done" before that.
