# CoinQuest
top down pokemon style rpg
# CoinQuest: Mascots of Mirage Chain  
### A Retro-Game-Boy-Color Inspired RPG Built in Remix

CoinQuest is a fully original, 90s-style creature-collector RPG using meme-coin mascots as the world’s monsters.  
The project uses a custom HTML5 canvas engine built inside Remix to emulate a Game Boy Color experience:

- 160×144 resolution  
- 8×8 tiles, 16×16 overworld sprites  
- Turn-based battles  
- Tile-based overworld movement  
- Full roster of original mascots  
- Multi-town overworld + routes + arenas  
- Modular architecture for expansion  

This repository contains the **full skeleton** for the complete game world, ready for expansion:
- All regions (towns, routes, caves, villain HQ, final tower)
- All mascots (base stats, types, evolutions)
- All moves, items, and systems
- Engine hooks for capturing, NPCs, story events
- Placeholder art files with pixel-art prompts

---

## 📦 Project Structure
/
├── app/
│ ├── game/
│ │ ├── engine/
│ │ ├── data/
│ │ ├── battle/
│ │ ├── world/
│ │ └── ui/
│ ├── routes/
│ ├── root.tsx
│ ├── styles.css
│ └── components/
├── assets/
│ ├── mascots/
│ ├── tilesets/
│ └── ui/
├── public/
│ └── placeholder.png
├── package.json
├── remix.config.js
├── tsconfig.json
└── GAME_SPEC.md

---

## 🛠 Getting Started
npm install
npm run dev

Open http://localhost:3000

---

## 📜 Notes

This repository ships with:
- Working overworld system  
- Working battle system  
- Complete mascot roster  
- All regions defined (maps are stubbed for safety)  
- Pixel art **prompts**, not actual artwork  
- All systems expandable by adding to `/app/game/data/*`

---

## 📚 See **GAME_SPEC.md** for the full world bible.



