# Prompt 04 — Metal Slug–Style Run-and-Gun

I want a side-scrolling run-and-gun arcade game that runs in the browser and captures what made Metal Slug special: dense, hand-crafted-looking pixel art, absurdly detailed animation, over-the-top explosions, cartoonish humor, and chaotic action that stays readable and fair. It has to feel like a lost arcade cabinet, not a game-jam demo. Chaos is the fun, but a skilled player should clearly beat a button-masher.

## Tech and limits

- TypeScript + Vite, rendered with the plain Canvas 2D API (no game engine). `npm install && npm run dev` must be all it takes. Everything runs client-side.
- No downloaded sprites, tilesets, fonts, music or sound files. Every sprite, animation frame, background layer, effect and sound is generated in code (drawing pixel art from code-defined palettes and pixel maps is expected).
- Render at a low internal arcade resolution (around 384×224) and scale up with crisp nearest-neighbor pixels. Hold a steady 60 fps even with 30+ enemies, hundreds of bullets and particles, and several explosions on screen.
- Controls: arrows or WASD to move, jump, shoot, grenade on separate keys (e.g. J / K / L), aim up by holding up, aim down while in the air, crouch while on the ground. Gamepad support is a strong bonus. Keys should be listed on the title screen.

## What the player goes through

1. **Attract mode and title.** A title screen with an animated logo for an original game name you invent, a short demo loop playing in the background, and "PRESS START".
2. **Character select.** Two or three soldiers with distinct looks and idle animations (cosmetic differences are enough).
3. **Mission.** One long, hand-designed level with at least four distinct sections, for example: a jungle riverbank, a bombed-out town, a moving train or bridge sequence, and an enemy fortress. The camera scrolls forward and sometimes locks in place for arena fights until the wave is cleared. Mid-level checkpoints.
4. **Boss.** A huge multi-part mechanical boss with several attack patterns, destructible components, phases that change as it breaks apart, and a spectacular death sequence.
5. **Mission complete.** A tally screen with score, POWs rescued, accuracy and time, then a return to the title. On a game over, offer "CONTINUE?" with a 10-second countdown.

## Gameplay systems (the core of the job)

- **Movement and shooting.** Tight, responsive controls with a slight arcade weight. The pistol has infinite ammo. Standing next to an enemy turns the shot into a knife attack. The soldier aims in 4 directions plus diagonals during transitions, just like the classic, and the upper body animates independently from the legs.
- **Weapon pickups.** Crates and rescued prisoners drop letter-coded weapons with limited ammo: heavy machine gun, shotgun, rocket launcher (homing), flamethrower, and one weapon you invent. Each should feel and sound completely different. When ammo runs out, you're back to the pistol.
- **Grenades.** Limited stock, arcing throw, bounce, explosion radius, with extra grenades as pickups.
- **Prisoners.** Tied-up bearded prisoners scattered across the level. Freeing them triggers a funny thank-you animation and a pickup drop. Some are hidden in destructible spots.
- **Vehicle.** At least one rideable vehicle (a small tank with a cannon and a machine gun turret) with its own health bar. You can hop out, and it explodes spectacularly when destroyed.
- **Destruction.** Walls, huts, crates, sandbags, watchtowers and vehicles break apart in stages. Destroyed things leave debris and smoke. Explosions push enemies and scatter pieces.
- **Scoring and lives.** Points for kills, prisoners and destruction, score popups, lives, and a combo/medal bonus for fast clears.

## Enemies

The enemy army should feel alive and funny, not like targets on rails:

- Several infantry types (rifleman, grenadier, shield-bearer, bazooka soldier, knife rusher), plus at least three vehicles or war machines (e.g. a small tank, a helicopter, a mortar crew or armored truck).
- Soldiers have personality: they chat, eat, sunbathe or goof around until they notice you, then panic, scream, run away or charge. Some play dead or hide behind cover.
- They take cover, lob grenades with believable arcs, and don't all fire at once. Enemy bullets are slow and visible enough to dodge.
- Multiple death animations depending on the weapon (burned by fire, blown into the air, sliced by the knife).
- Difficulty ramps across the level with new enemy combinations, never unfair spikes.

## Presentation

- Multi-layer parallax backgrounds with animated details (smoke, birds, water, burning ruins, moving clouds).
- Heavy screen shake, hit flashes, muzzle flashes, shell casings, blood-free cartoon violence, big layered explosions with debris and fire.
- Arcade HUD: player score, lives, current weapon with ammo counter, grenade count, credits, and boss health bar.
- Chiptune-flavored soundtrack synthesized in code with different tracks for level, boss and victory, plus punchy SFX (each gun, explosions, pickups, prisoner "thank you" jingle, a synthesized announcer-style voice cue like "MISSION START!" if you can pull it off).

## What I expect at the end

A finished game playable from title screen to mission complete. Not a vertical slice, not a tech demo. Get it running, play through it yourself, fix everything that feels broken or unfair, then polish it until it looks and sounds like it belongs in an arcade. Blow me away.
