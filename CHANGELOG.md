# Changelog

All notable changes to the **AlphaBits** project will be documented in this file.

## [v1.1.0] - 2026-01-08
### 🎨 Visual & Animation Update
- **Lip-Sync System**: Implemented dynamic mouth movement. Characters now open/close mouths in sync with speech duration.
- **Idle Animations**: Added "Blinking" logic. Characters randomly blink when not speaking to feel more alive.
- **Asset Upgrade**: Migrated all character assets to **Transparent PNG** format to remove background artifacts.
- **Core Engine**: Switched rendering method to `ImageSequenceClip` for precise frame-by-frame animation control.

## [v1.0.0] - 2026-01-08
### Initial Release
- **Branding**: Project named "AlphaBits".
- **Characters**: Added **KING** (Cat) and **DUCK** (Bot) assets.
- **Engine**: Implemented the `run_pixel.py` script for video generation.
- **Audio**: Added **"Live-Voice" Logic**. The system now slices random segments from long emotional WAV files to create natural-sounding "gibberish" speech (Undertale/Animal Crossing style).
- **Structure**: Repository organized for open-source contribution.