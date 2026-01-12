# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Current Version:** v8.0 (PC Master Race Edition)
> **Release Date:** 2026-01-13

---

## [v8.0] - The "PC Master Race" & 1080p Overhaul 🚀
**Massive Performance & Quality Update.**
Migrated the rendering pipeline from cloud-based CPU rendering to a high-performance local architecture (i5-14600KF / RTX 4070 optimized). Achieved **10x faster render speeds** while increasing resolution to Native 1080p.

### ⚡ Core Engine: "Smart Upscale" Pipeline
* **FFMPEG Hardware Acceleration:** Completely rewrote the rendering logic. Instead of resizing frames pixel-by-pixel in Python (slow), the engine now renders in a lightweight 960x540 canvas and uses FFMPEG's `neighbor` filter to upscale to **1920x1080** on the fly.
    * **Result:** Render time dropped from **7 minutes** to **~45 seconds**.
    * **Quality:** Crystal clear pixel art with zero blur.
* **Multi-Threading Unleashed:** Unlocked the thread limit. Increased from `threads=4` to `threads=16` to fully utilize modern 14+ core CPUs.
* **Bitrate Boost:** Increased bitrate to **10,000k** to eliminate compression artifacts and "red pixel" noise.

### 🔊 Audio Sync & Timing Fixes
* **Drift Elimination:** Fixed a critical bug where audio dialogue would start before the video animation.
* **Logic Change:** Removed manual audio concatenation. The engine now binds audio clips directly to video segments, ensuring perfect lip-sync even during pauses/silence.

### 🎨 Visual & UI Polish
* **Infinite Topic Bar:** Increased the ticker tape loop factor from `3x` to `30x`. The topic bar now runs infinitely and never disappears, regardless of video length.
* **Stage Composition:**
    * **Hobo Position:** Moved Hobo significantly closer to the fire (`x=1100`) for a more natural, cozy composition.
* **Smart Text Wrapping:** Adjusted the text bubble constraints. Reduced text width limit (`width=25`) and increased padding to prevent text from clipping out of the speech bubbles on 1080p resolution.

---

## [v7.2] - The "We Are So Back" Update 📈
* **Added `THREADGUY` to the roster.**
* **Twitch Aesthetic:** Implemented purple color schemes.

## [v7.1] - The "Vitalik & Atmosphere" Update 🦄
* **Added `VITALIK` to the roster.**
* **Weather Engine:** Implemented smooth gradient transitions for rain and snow.