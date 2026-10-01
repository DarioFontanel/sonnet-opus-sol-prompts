# Prompt 01 — Claude Code: Terminal vs Desktop App

Build an 18-second animated short in portrait format (1080×1920, 30 fps) using only JavaScript and an HTML `<canvas>`. Deliver a single standalone HTML file where every visual is generated in code: no external images, no video clips, no animation frameworks (loading Google Fonts is allowed).

Subject: Claude Code in the terminal vs. Claude Code in the desktop app. Get the substance right: it is the same agent underneath in both cases (same models, same tools, same project instructions from CLAUDE.md, same permission prompts). What changes is the surface you drive it from. The terminal version lives inside your shell: keyboard-first, text-only, easy to script and pipe, and usable on a remote machine over SSH. The desktop app wraps that same agent in a visual interface: several sessions visible side by side, each able to work in its own isolated git worktree, with changes shown as diffs you can review before accepting them. The viewer should leave understanding "same brain, two cockpits", and roughly when each one fits better.

Visual direction: a cut-paper collage look, as if the scenes were built from torn and layered paper shapes. Everything else (characters, metaphors, transitions, rhythm, composition) is your call.

Treat it as a real piece of content for Reels/TikTok/Shorts: hook the viewer within the first second, keep all text legible on a phone screen (remember that the app interface hides roughly the lowest 380 px and a vertical band along the right side), stick to one clear message, and end on a moment that feels rewarding. Add background music and sound effects generated with the Web Audio API.

Technical requirements:

* Provide a `renderFrame(t)` function that paints the frame at time `t` in a fully deterministic way: the same `t` must always produce identical pixels, so any randomness must come from a seeded generator (never `Math.random()` or the system clock). Also provide a function that renders the whole soundtrack offline and returns it as a WAV.
* When the HTML file is opened in a browser, it should play a real-time preview.
* Include an export script (Node + Playwright + ffmpeg) that renders all 540 frames, muxes them with the audio into `final.mp4`, and actually run it to produce the finished video.
