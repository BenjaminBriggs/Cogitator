---
name: cogitator
description: >
  Warhammer 40,000 (10th Edition) knowledge centre with full unit datasheets,
  detachment rules, army rules, stratagems, enhancements, core abilities, and
  universal stratagems for all factions. Use this skill whenever the user asks
  about a specific unit's stats, weapons, abilities, points, wargear options,
  keywords, who can lead a unit, detachment stratagems, enhancements, army
  rules, faction abilities, or any "what does X do" / "what are the stats for Y"
  question about WH40K 10th edition. Also trigger when the user is comparing
  units, building army lists, checking weapon profiles, asking about detachment
  choices, or needs to know how a faction ability works. If the user mentions any
  WH40K unit, faction, or detachment by name, use this skill — even if they
  don't explicitly say "40K" or "Warhammer".
---

# Cogitator — WH40K Knowledge Centre (10th Edition)

You have access to a comprehensive extracted dataset of Warhammer 40,000 10th
Edition rules. This is your primary source for unit stats, weapon profiles,
abilities, detachment rules, stratagems, enhancements, and army rules.

Always read the relevant file(s) before answering. Do not rely on memory —
this dataset is authoritative.

## Data location

All paths are relative to this skill file's directory.

## Dataset structure

```
global/
├── core-abilities.md        — Universal abilities (Deep Strike, FNP, Deadly Demise, etc.)
└── universal-stratagems.md  — Stratagems available to all armies

factions/
└── <faction-slug>/
    ├── <faction-slug>.md        — Army rules, faction ability, detachment list, datasheet index
    ├── datasheets/
    │   └── <unit-name>.md       — Full datasheet per unit
    └── detachments/
        └── <detachment-name>.md — Detachment ability, stratagems, enhancements
```

## Faction directory

| Faction | Slug | Datasheets | Detachments |
|---|---|---|---|
| Adepta Sororitas | `adepta-sororitas` | 37 | 7 |
| Adeptus Custodes | `adeptus-custodes` | 31 | 8 |
| Adeptus Mechanicus | `adeptus-mechanicus` | 36 | 9 |
| Adeptus Titanicus | `adeptus-titanicus` | 4 | 0 |
| Aeldari | `aeldari` | 97 | 16 |
| Astra Militarum | `astra-militarum` | 128 | 9 |
| Chaos Daemons | `chaos-daemons` | 105 | 10 |
| Chaos Knights | `chaos-knights` | 37 | 5 |
| Chaos Space Marines | `chaos-space-marines` | 110 | 16 |
| Death Guard | `death-guard` | 71 | 10 |
| Drukhari | `drukhari` | 47 | 10 |
| Emperor's Children | `emperors-children` | 22 | 7 |
| Genestealer Cults | `genestealer-cults` | 136 | 9 |
| Grey Knights | `grey-knights` | 31 | 8 |
| Imperial Agents | `imperial-agents` | 45 | 7 |
| Imperial Knights | `imperial-knights` | 27 | 5 |
| Leagues of Votann | `leagues-of-votann` | 22 | 9 |
| Necrons | `necrons` | 64 | 12 |
| Orks | `orks` | 86 | 11 |
| Space Marines | `space-marines` | 290 | 40 |
| T'au Empire | `tau-empire` | 63 | 8 |
| Thousand Sons | `thousand-sons` | 60 | 9 |
| Tyranids | `tyranids` | 56 | 12 |
| Unaligned Forces | `unaligned-forces` | 20 | 0 |
| World Eaters | `world-eaters` | 58 | 8 |

## How to look things up

### The index — your starting point

`factions/index.md` is a complete file index covering every faction overview,
detachment, and datasheet in the dataset. Each line has the format:

```
<relative-path> — <unit/detachment name> — <role> [points]
```

Grep the index to find the right file path, then read that file:

```bash
# Find a unit across all factions
grep -i "intercessor" factions/index.md

# Find a detachment
grep -i "gladius" factions/index.md

# Find all battleline units for a faction
grep -i "battleline" factions/index.md | grep -i "space-marines"
```

The index is ~1,700 lines — always grep it, never read it in full.

### Finding an army rule or faction ability

Read `factions/<faction-slug>/<faction-slug>.md` — army rules are at the top of
the file. You can also grep the index for the faction overview file:

```bash
grep "army rules" factions/index.md | grep -i "necrons"
```

### Finding a core ability (Deep Strike, Feel No Pain, etc.)

Read `global/core-abilities.md`.

### Finding a universal stratagem

Read `global/universal-stratagems.md`.

## Datasheet format

Each datasheet markdown file contains (in order):

1. **Unit name** (H1)
2. **Role** (Battleline, Dedicated Transport, etc.)
3. **Flavour text**
4. **Stat block table** — M, T, Sv, W, Ld, OC (may have multiple rows for mixed-stat units)
5. **Invulnerable Save** (or `-` if none)
6. **Default Wargear**
7. **Ranged Weapons table** — Name, Range, A, BS, S, AP, D, Keywords
8. **Melee Weapons table** — Name, Range, A, WS, S, AP, D, Keywords
9. **Abilities** — Faction abilities, datasheet abilities, with full rules text
10. **Keywords** and **Faction Keywords**
11. **Unit Composition** — model types and count ranges
12. **Wargear Options** — what can be swapped for what
13. **Leader** / **Led By** — which characters can attach
14. **Points** — per model count

## Detachment format

Each detachment file contains:

1. **Detachment name** (H1)
2. **Detachment ability** — the core passive/active rule
3. **Stratagems** — each with name, CP cost, type, timing (turn/phase), full
   WHEN/TARGET/EFFECT/RESTRICTIONS text
4. **Enhancements** — name, points cost, eligibility, effect

## Answering questions

### Unit stats / weapon profiles
Read the specific datasheet. Quote the stat line and weapon table directly.

### "Can unit X take weapon Y?"
Read the datasheet's Wargear Options section. Be precise about which model in
the unit can take it and any conditions (e.g. "for every 5 models").

### "What detachments does faction X have?"
Read `factions/<faction-slug>/<faction-slug>.md` — detachment list is near the top.

### "What does detachment ability X do?"
Read the specific detachment file.

### "Who can lead unit X?"
Read the datasheet's Leader/Led By section.

### Comparing units
Read both datasheets and present stats side-by-side in a table.

### Army list building
Read relevant datasheets for points, composition, and keywords. Check
detachment for synergies.

## Quick reference: common keyword effects

These weapon keywords appear throughout datasheets. Knowing them helps you
interpret stat tables without needing to look up the core rules every time:

| Keyword | Effect |
|---|---|
| `assault` | Can shoot after Advancing (no penalty) |
| `heavy` | +1 to Hit if unit Remained Stationary |
| `rapid fire N` | +N Attacks if target within half range |
| `melta N` | +N Damage if target within half range |
| `blast` | Min 3A vs 6+ models, min 6A vs 11+ models |
| `torrent` | Auto-hits (skip Hit roll) |
| `twin-linked` | Re-roll failed Wound rolls |
| `lethal hits` | Critical Hits auto-wound |
| `devastating wounds` | Critical Wounds become mortal wounds |
| `sustained hits N` | Critical Hit generates N extra hits |
| `anti-X N+` | Critical Wound on N+ vs keyword X |
| `hazardous` | After shooting, D6 per weapon; 1 = 3 mortal wounds to bearer |
| `pistol` | Can shoot in engagement range, only at units in engagement range |
| `ignores cover` | Target doesn't benefit from cover |
| `indirect fire` | Can target non-visible units; -1 to Hit, target gains cover |
| `precision` | Can allocate to Character models |
| `lance` | +1 to Wound on charge turn |
