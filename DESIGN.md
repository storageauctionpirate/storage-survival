# Storage Survival: The Tweaker Apocalypse — rough draft
Top-down arcade survival. Single `index.html`, vanilla JS + canvas.
## Rules
- Move through a facility (aisles + building blocks with red roll-up doors). Swing at a closed door to open it: loot = cash (60%), health +30 (25%), bug spray x3 (15%; each charge adds a 110px area blast to a swing).
- Enemies spawn at map edges (sometimes out of opened units): roaches (fast, weak, spawn in 3s), rats (medium), tweakers (slow, tough, goofy cartoon scavengers with orange hair, googly eyes, a stolen lamp).
- Survive the wave timer to clear the facility (+500×wave bonus, +25 HP). 4 handmade facilities, then endless scaling (×1.15 spawn rate and enemy HP each).
- HUD: HP, cash, score, wave/timer, spray count, facility name.
## CONFIG
`CONFIG` at the top: tile/map size, player (speed, hp, range, dmg, cooldown), enemies (hp, speed, dmg, radius, score), facilities (waveTime, spawnEvery, mix, units), endlessScale, loot weights.
Core logic is in `StorageSurvival` (newGame/update(dt,input)/next/state), separate from the rendering and input shell, so it can be embedded as a mini-game later.
Test hooks: `#howto`, `#play`, `#sim` (simulates 15s of play), `#demo`.
## Open questions
- Should cash carry over into the bigger game's economy? Is there a shop between facilities?
- Should the difficulty curve and wave lengths be tuned after friend feedback?
- Should we add sound, sprite art from the AI cast, or a boss tweaker ("The Unit Squatter")?
- Should we add a high-score save (localStorage)?
