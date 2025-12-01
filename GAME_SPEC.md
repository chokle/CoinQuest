# GAME_SPEC – CoinQuest: Mascots of Mirage Chain  
### Full World Bible — Version 1.0  
### Engine Type: Retro Canvas Engine (GBC-Style)

---

# 0. Objective
CoinQuest is a fully original 90s-inspired creature-collector RPG.  
Your creatures are **meme coin mascots**, each with unique personalities, evolutions, types, and moves.

This document defines:

- The full world (towns, routes, caves, tower, villain base)
- The 30+ mascots (types, stats, evolutions, descriptions)
- Moves, items, status effects
- Storyline, arenas, rival, villain team
- Pixel-art direction for all assets
- Game Boy Color–style constraints
- How the Remix engine implements everything

---

# 1. GBC-Style Constraints

- **Resolution:** 160×144  
- **Tiles:** 8×8  
- **Overworld sprites:** 16×16 (2×2 tiles)  
- **Battle sprites:** 48×48  
- **Palette:** 4-color per sprite; GBC-style color ramp  
- **Audio:** chiptune 4-channel style  
- **Tilemaps:** Up to 256 tiles per tileset  

The engine emulates these visually, not byte-exact.

---

# 2. Types

- **Meme**
- **Tech**
- **Beast**
- **Element**
- **Cosmic**
- **Shadow**

Type chart fully defined in `app/game/data/types.ts`.

---

# 3. Mascots

The complete roster is 31 mascots:

### Starters (3 lines, 3-stage)
- Chucklepup → Memehound → Gigrin (Meme/Beast → Meme/Beast → Meme/Cosmic)  
- Sproutcoin → Bloomcoin → Verdantor (Element → Element → Element/Beast)  
- Bitflit → Byteflare → Chainflare (Tech → Tech/Element → Tech/Cosmic)

### Early Mascots (Route 1)
- Frognote (Beast/Meme)  
- Clinkbat (Tech)  
- Tidelink (Element)  
- Shellbyte → Tidevault (Beast/Tech → Beast/Element)

### Mid Mascots
- Hashmole → Hashdrill  
- Glitchkit → Bugstack  
- Lumiloom  
- Owlrate → Bullrate

### Late Mascots
- Mooncoin → Ecliptor  
- Ghostrug → Rugreaper  
- Neburon (Semi-Legendary)  
- Chainseer (Rare)

Full stats, evolutions, learnsets in `/app/game/data/mascots/*`.

---

# 4. Moves
Full move list (~40 moves) defined in:
app/game/data/moves/basic.ts
app/game/data/moves/status.ts
app/game/data/moves/advanced.ts

All moves have:
- Type  
- Category (physical, special, status)  
- Power  
- Accuracy  
- PP  
- Optional effects  

---

# 5. Status Effects

- **Burned** – ATK reduced  
- **Paralyzed** – speed halved  
- **Glitched** – chance to hurt self  
- **Drowsy** – delayed sleep  
- **Drained** – HP drain  

---

# 6. World Regions
The region **Ledgera** has:

### Towns
1. Startbyte Town  
2. Blockport Village  
3. Hashpeak City  
4. Fluxgrove Town  
5. Neonode City  
6. Lunaris Harbor  
7. Mirage Tower summit

### Routes
Bytepath Road (R1)  
Pierway Trail (R2)  
Miner’s Climb (R3)  
Glitchwood Path (R4)  
Neonline Route (R5)  
Starlit Coastal (R6)

### Dungeons
Hashpeak Tunnel  
Voidrift Cavern  
Team Rugpull HQ  
Mirage Tower

Each map is defined structurally but content-light to avoid bloat.

---

# 7. Storyline

- Rival: **Kira**  
- Scientist: **Dr. Ledger**  
- Villain Team: **Team Rugpull**  
- Badges: 5 total (starter skeleton)  
- Final showdown in **Mirage Tower**

---

# 8. Art Direction

## Overworld sprites
16×16, 4 colors, thick outlines, no AA, subtle dithering.

## Battle sprites
48×48, 4 colors, GBC shading style.

## Tilesets
- Grassland  
- Mountain  
- Forest  
- Neon city  
- Cosmic/void  

Every file in `/assets/*` contains a **pixel art prompt**.

---

# 9. Engine Architecture

/app/game/
engine/ # core loop, input, rendering
battle/ # turn system, damage, status
data/ # mascots, moves, items, maps
world/ # map loader, collisions, interaction
ui/ # dialog, menus, battle hud

---

# 10. Expansion Guide

To add new mascots:

1. Add to `/app/game/data/mascots`  
2. Add moves to `/app/game/data/moves`  
3. Add encounter tables  
4. Add sprite prompt files to `/assets/mascots`

---

# End of GAME_SPEC.md
