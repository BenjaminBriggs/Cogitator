<p align="center">
  <img src="Cogitator.jpg" alt="Cogitator" width="200">
</p>

# Cogitator

A Claude skill for Warhammer 40,000 (10th Edition) — query the complete dataset of unit datasheets, detachment rules, army rules, stratagems, and enhancements across all factions.

## What's included

- **1,683 unit datasheets** — full stat blocks, weapon profiles, abilities, wargear options, points, keywords, and leader attachments
- **245 detachment files** — detachment abilities, stratagems, and enhancements
- **26 faction overviews** — army rules, faction abilities, detachment and datasheet indices
- **Core abilities & universal stratagems** — Deep Strike, Feel No Pain, Deadly Demise, and all shared stratagems
- **Searchable index** — grep-friendly file index for fast lookups across ~1,700 entries

## Structure

```
cogitator/
├── SKILL.md              — Skill instructions and lookup guide
├── global/
│   ├── core-abilities.md
│   └── universal-stratagems.md
└── factions/
    ├── index.md          — Searchable file index
    └── <faction-slug>/
        ├── <faction-slug>.md
        ├── datasheets/
        └── detachments/
```

## Installation

1. Download or clone this repo
2. Place the folder in your Claude Code skills directory or upload via Claude.ai Settings > Capabilities > Skills

## Usage

Ask Claude anything about WH40K 10th Edition units, weapons, detachments, or army rules. The skill activates automatically when it detects a relevant query.

**Examples:**
- "What are the stats for Intercessor Squad?"
- "What detachments do Necrons have?"
- "Can a Canoness take a plasma pistol?"
- "Compare Boyz vs Hormagaunts"
- "What enhancements does the Gladius Task Force have?"

## License

This skill is a fan-made reference tool. Warhammer 40,000 is a trademark of Games Workshop Ltd. All game content belongs to Games Workshop.
