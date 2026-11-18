# Sam's Rainy Dublin

A 2D side-scrolling platformer for PC and mobile. Level 01 runs from Temple Bar to the Ha'penny Bridge.

## Play

Double-click `index.html`. It needs no installation or build step.

| Action | PC | Mobile |
| --- | --- | --- |
| Move | Arrow keys or A/D | On-screen pad |
| Run | Keep holding a direction, or hold Shift | Keep holding a direction |
| Jump | Space (hold to jump higher) | JUMP button (hold to jump higher) |
| Throw flip-flop | F or X (hold to keep throwing) | THROW button (hold to keep throwing) |
| Block | Hold S, C or Down | Hold BLOCK |
| Team special (Level 2) | Q or V when the pink meter is full | SPECIAL button |
| Swap hero (Level 3) | Tab or E | SWAP button |
| Music on or off | M | Not available |
| Pause | P or Esc | Pause button |

To test on a phone, the folder must be hosted somewhere the phone can reach.

## Project layout

| Folder | What it holds |
| --- | --- |
| `src/core` | Game loop, rules, settings, input and image loading |
| `src/player` | Sam's movement, animation poses and drawing |
| `src/level` | Level data, with one file per Dublin section |
| `src/environment` | Parallax layers, rain, buildings, platforms and art cropping |
| `src/physics` | Collision |
| `src/enemies` | Pigeon, seagull, keg and The Ex Husband boss |
| `src/weapons` | Sam's flip-flop |
| `src/collectibles` | Coins, shamrocks, checkpoints and the finish gate |
| `src/camera` | Camera that follows Sam |
| `src/ui` | HUD, menus and touch controls |
| `src/story` | Opening, ending scenes and the Level 02 transition |
| `assets/source` | Your original illustrations |
| `tools/art-grid.html` | Helper for measuring new crops from an illustration |

## Common changes

- **Tune the game feel:** edit `src/core/config.js`.
- **Change a level section:** edit its file in `src/level/sections`. The fields are listed at the top of `src/level/levelKit.js`.
- **Add a section:** copy a section file, add its script to `index.html`, then list it in `src/level/level01.js`. Every section must start and end at ground height.
- **Add an enemy:** copy `src/enemies/pigeon.js`, register the new type, and add its script to `index.html`.
- **Change the story text:** edit `src/story/level01Story.js`.
- **Start Level 02:** replace `showNextChapterScreen` in `src/core/game.js`.
- **Tune the boss:** health, hit protection and attack order are at the top of `src/enemies/exHusband.js`.
- **Tune the flip-flop:** speed, throw rate and aim assist are at the top of `src/weapons/flipFlops.js`.
- **Use new scenery art:** add the image to `src/core/assets.js`, define its crop in `src/environment/artAtlas.js`, then use it in a section's `backdrop`.
- **Use final Sam sprites:** replace `RD.SamRig.draw` in `src/player/samRig.js`. The animation states are already in place.

## Temporary art

These are painted in code until final art is ready:

- Sam's in-game body and her six animations
- Pigeons, seagulls and kegs
- The Ex Husband and the flip-flop
- Buildings outside the two supplied street scenes
- River, Ha'penny Bridge, lamps and stone platforms
