# ARCHITECTURE.md — ElfStory Gone Wild

## Big picture

Two layers, built in order:

1. **v1 Prototype (Phase 1, in parallel build):** a single-file HTML canvas game that proves the whole loop end-to-end — overworld hub, drivable truck, race, shop, repeat. Fast to ship, easy to play-check, disposable if the loop doesn't slap.
2. **Full Port (Phase 2):** port the actual Elfstory3d TypeScript / Three.js codebase (full-3D, Overhead Tactical + Chase) into this repo and retheme zones / NPCs / quests on top of the proven prototype loop.

Source game: **Garthnesss/Elfstory3d** — full-3D dungeon crawler, Overhead Tactical (default) + Chase (alternate, `V` cycles), Oakhaven village hub, Sunken Citadel dungeon.

This repo: **Garthnesss/elfstorygonewild**, public, created Nov 15, 2026, initial head `498cc646` (README only at creation).

## Components

### 1. RADHAVEN — Overworld Hub (Mode 1, v1 prototype)
- Top-down / canvas hub retheming Oakhaven → RADHAVEN.
- Player walks as Garth, talks to NPCs, and can get in / drive the monster truck.
- Truck driving in overworld: crush parked cars for cash.
- Collectible energy drink cans (VOLTAGE DEW / CRIMSON BULL / BEAST ENERGY) scattered in world — powerup / currency flavour, see DESIGN_BIBLE.md.
- NPCs: Roxy Rampage, Vixen Voltage, Cherry Bomb, Dixie Dewdrop, Mama Max — each with role, dialogue in extreme slang, and a gameplay function (shop, race entry, freestyle, Pit Party, championship).
- Exit points: race entry (Super Off Road Remix), Freestyle arena (planned), dungeon / Sunken Stadium route (Phase 2).

### 2. SUPER OFF-ROAD REMIX — Race (Mode 2, v1 prototype)
Directly modelled on **Ivan "Ironman" Stewart's Super Off Road** (Leland arcade 1989, SNES 1992):
- Top-down, **single screen** — whole track visible at once, no scrolling / no split-screen.
- **4 trucks, 4 laps.**
- Player truck: GARTH'S MEGA MONSTER vs 3 AI rivals.
- Pickups on track: **nitro** (tap to boost) + **cash bags** (banked to shop money).
- Finish position → prize money → straight into the Speed Shop.
- AI rivals: simple racing line + rubber-banding tuned so last place is recoverable and first place is never safe, no cap.

### 3. VIXEN'S SPEED SHOP — Between Races (Mode 3, v1 prototype)
- Owner / mechanic: Vixen Voltage, pit crew chief.
- Opens between every race. Spend prize + crushed-car + cash-bag money on 5 categories, mirroring the original arcade shop structure:
  - Nitro — consumable, bought per unit
  - Tires — tightens turning
  - Shocks — less bounce
  - Acceleration — faster off the line / out of corners
  - Top Speed — higher max velocity
- Original arcade prices (for reference, cited in DESIGN_BIBLE.md): Nitro $1,000 each (max 99), Tires $40,000, Shocks $60,000, Acceleration $80,000, Top Speed $100,000, each non-nitro upgrade max 5 levels.
- **Our in-game prices are scaled down** for this game's economy, but keep the same 5 categories + structure (max 5 levels non-nitro, nitro as a stackable consumable).

### 4. FREESTYLE ARENA — Scoring Mode (Planned, Phase 3)
- Monster Jam Freestyle structure: big air, backflips, donuts, wheelies, car crushing, timed run, fan judging.
- 2-Wheel Skills: wheelies / stoppies / bicycles scored separately.
- Bracket Racing: head-to-head single-elimination bracket, Monster Jam Racing format.
- Pit Party: pre-show hub event — meet drivers, see trucks up close, hosted by Dixie Dewdrop.
- In v1 architecture this is a planned mode slot off RADHAVEN; it does not block the Phase 1 loop.

### 5. Full 3D Layer (Phase 2)
- Ported Elfstory3d TS/Three.js engine: Overhead Tactical + Chase cameras, zones, quests, saves, skills — rethemed, not rewritten from scratch where the original system already works.
- Retheme map lives in DESIGN_BIBLE.md (e.g. Oakhaven → RADHAVEN, Sunken Citadel → THE SUNKEN STADIUM).

## Data flow

```
RADHAVEN (walk / talk / drive / crush cars / collect cans)
        │
        ├── cash ──────────────────────────────┐
        ▼                                      │
SUPER OFF-ROAD REMIX (4 trucks, 4 laps)        │
   nitro pickups ──► boost in-race             │
   cash bags ──────► banked cash ──────────────┤
   finish place ───► prize money ──────────────┤
        ▼                                      ▼
VIXEN'S SPEED SHOP ◄──────────────────── total cash
   buy Nitro / Tires / Shocks / Accel / Top Speed
        │
        └── upgraded truck stats ──► next race (loop)
        │
        └── (Phase 3) FREESTYLE / 2-WHEEL / BRACKET / PIT PARTY
```

Truck state is the shared spine: one persistent truck record (upgrade levels 0–5 per non-nitro category, nitro count, cash) read by the overworld driver, the race sim, and the shop. No mode keeps its own private copy.

## Dependencies

- v1 prototype: plain HTML + Canvas + vanilla JS in a single file. No build step, no CDN dependency for core play (deliberate — it must load offline and on a phone).
- Phase 2 port: TypeScript + Three.js + Vite, inherited from Elfstory3d, plus its `tools/build-pages.py` single-file Pages bundle approach.
- Hosting: GitHub Pages (Phase 4), same pattern as Elfstory3d / ElfStory.
- No external APIs, no accounts, no backend. Saves are local (browser storage), disposable during testing per the Elfstory3d precedent.

## What's missing

- Everything playable is still **planned / in parallel build** — no mode is verified until STATUS.md says so.
- No save schema defined yet for truck upgrades across the 3D port (Phase 2 decision).
- No phone / touch controls designed yet (Phase 4).
- No audio design yet (engine, crowd, announcer lines) — Cherry Bomb's voice is a Phase 3/4 problem.
- Freestyle scoring rubric not yet tuned (trick values, fan-judging weights) — Phase 3.
- No REA-Results prior art to reuse: local mirror checked Nov 15, 2026, no matching entry (see DESIGN_BIBLE.md).
