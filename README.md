# The Hollow Below

An original playable 3D horror sandbox prototype built with Three.js. The world is a side-scrolling voxel diorama: movement is constrained to a 2D plane, with real 3D geometry, perspective, lighting, and depth. Desktop keyboard and mouse required.

## Launch

Requires Node.js 20.19+ or 22.12+ (tested with Node 24).

```sh
npm ci --cache /tmp/hollow-npm
npm run dev -- --port 5173
```

Open the development server in a browser with WebGL support. Click **Enter the Hollow** to activate sound and play. `npm run build` creates `dist/`; `npm run preview` serves the production build.

## Controls

| Input | Action |
| --- | --- |
| A / D or left / right | Move |
| Space / W / up | Jump |
| Left mouse (hold) | Mine within reach |
| Right mouse | Place selected material, adjacent to terrain |
| 1–5 or hotbar click | Select wood, dirt, stone, ore, or torch |
| F (hold) | Melee attack in facing direction |
| E | Open / close crafting (pauses simulation) |
| Q | Place a torch at your feet |
| R | Drink a crafted remedy |
| M | Mute audio |
| H | Help and new-world button (pauses simulation) |

## First-night loop

Gather wood from trunks and stone from underground. Craft a stone pickaxe for faster mining. Add five blocks to the ruined shelter and keep a torch nearby; the shelter restores health. Head east to the open shaft near world column 39. Mine glowing ember ore, craft an ember blade or healing remedies, and survive a creature encounter. Return to shelter to complete the journal. The sandbox continues afterward.

Dusk and night alternate every 70 seconds. Threats spawn more often at night. Light repels creatures and dissolves the Witness's projectiles. The **Witness**, a red-robed dark magician with a hollow hood, casts echoes; the **Maw**, a red-robed demon with a huge toothed mouth and floating fragments, closes in for melee attacks. Both are original simplified voxel interpretations of the supplied second and third enemy designs.

## Implemented

One small surface, an underground cave with a deeper pocket, destructible/placeable blocks, movement and jumping, inventory and hotbar, four recipes, tool upgrades, melee combat, two enemy types, hostile projectiles, light-based safety, shelter recovery, health/death/respawn, day/night spawning, ambient drone and action sounds, and a first-night objective tracker.

## Prototype limitations

No persistent saves: refreshing or starting a new world resets progress. Respawning preserves the current in-memory terrain and inventory. No multiplayer, touch controls, gamepad support, fluid simulation, advanced enemy navigation, doors, or extended progression. Enemy art is built from voxel geometry rather than exact sprites from the reference. Audio is synthesized and minimal. Shelter detection is a simple nearby-built-block and torch heuristic, not a fully enclosed-room simulation. The visual style uses low-resolution rendering and scanlines; it is not a full pixel-texture art pipeline.

## Validation

Production build passes. Headless Chromium/WebGL browser checks found no runtime exceptions and verified opening crafting, torch placement, terrain mining/resource gain, block placement/resource cost, pickaxe crafting, and a melee hit against the Maw. Complete manual survival balancing remains to be playtested.
