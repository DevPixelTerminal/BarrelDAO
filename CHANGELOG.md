# 📜 BarrelDAO Change Log

All notable changes to the **"Night Shift Terminal"** simulation engine will be documented in this file.

> **Current Version:** v8.5 (God Tier Update)
> **Release Date:** 2026-01-17
> **Engine:** Python 3.12 + OpenAI GPT-4o + FFMPEG High-Profile

---

## [v8.5] - The "King of Retail" & High-Fidelity Asset Update 👑
**Major Content Expansion & Asset Pipeline Upgrade.**
This update introduces the most complex character model to date and refines the asset loading pipeline to support high-resolution PNG transparency, enabling a new tier of visual quality.

### 🆕 New Character: ANSEM (@blknoiz06)
* **Archetype Integration:** Added "The King of Retail" to the guest rotation.
* **High-Fidelity Sprites:** Implemented a new, high-detail pixel art style (Stardew Valley / Eastward aesthetic) specifically for this character.
    * **Visual Details:** Accurate representation of the "fade" haircut, glasses, beard, and signature streetwear (Bitcoin hoodie).
    * **Unique Animation:** Added a custom "Phone Check" idle state where the character is constantly engaged with the market.
* **Personality Engine:** Tuned the GPT-4o prompt to reflect his specific Twitter persona ("God Tier calls", "Solana maximalism", "Smug confidence").

### 🛠️ Engine & Asset Improvements
* **PNG Alpha Channel Support:** Upgraded the `load_trimmed()` function to correctly handle high-bit-depth PNG files with complex transparency layers. This solves issues with "halo" artifacts around detailed sprites.
* **Asset Mix-and-Match:** The engine now seamlessly handles a mix of legacy `.jpg` assets and new high-quality `.png` assets within the same scene.
* **Dialogue Tuning:** Adjusted the "Slang Filter" to include newer market terminology ("Liquidity", "Thesis", "Send it").

---

## [v8.0] - The "PC Master Race" & 1080p Overhaul 🚀
**Massive Performance, Architecture & Quality Update.**
Successfully migrated the rendering pipeline from a cloud-based CPU environment to a high-performance local architecture (optimized for **i5-14600KF / RTX 4070**). Achieved a **1200% increase in render speed** while doubling the output resolution.

### ⚡ Core Engine: "Smart Upscale" Pipeline
* **FFMPEG Hardware Acceleration:** Completely rewrote the rendering logic to bypass Python's slow resizing methods. The engine now renders frames in a lightweight native 960x540 canvas and utilizes FFMPEG's `neighbor` filter to upscale to **1920x1080 (Full HD)** during the encoding pass.
    * **Result:** Render time dropped from **~7 minutes** to **~45 seconds** per episode.
    * **Visuals:** Achieved pixel-perfect sharpness with zero anti-aliasing blur.
* **Multi-Threading Unleashed:** Unlocked the thread limiter. Increased encoding threads from `4` to `16` to fully utilize the 20-thread capacity of the new hardware.
* **Bitrate Boost:** Increased video bitrate to **10,000k (10 Mbps)** to eliminate all compression artifacts and "red pixel" noise in dark scenes.

### 🔊 Audio Sync & Timing Fixes
* **Drift Elimination:** Fixed a critical synchronization bug where audio dialogue would "run ahead" of the video animation during silence/walking sequences.
* **Logic Overhaul:** Removed manual `concatenate_audioclips` stitching. The engine now binds audio clips directly to specific video segments, ensuring perfect lip-sync even during procedural pauses.

### 🎨 Visual & UI Polish
* **Infinite Topic Bar:** Increased the ticker tape loop factor from `3x` to `30x`. The scrolling topic bar is now mathematically guaranteed to never disappear, regardless of dialogue length.
* **Stage Composition:**
    * **Hobo Position:** Adjusted world coordinates (`x=1100`) to place the Host closer to the fire barrel, creating a more natural, "warming hands" composition.
* **Smart Text Wrapping:** Recalculated text bubble constraints for 1080p. Reduced text width limit (`width=25`) and increased padding to prevent text clipping.

---

## [v7.2] - The "We Are So Back" Update 📈
**Roster Expansion.** Injected pure "Crypto Twitter" chaos into the simulation.
* **New Character: THREADGUY:** Added the "Degen Streamer" archetype.
    * **Assets:** Custom white hoodie (Twitch logo), messy hair, grey sweatpants.
    * **Behavior:** Unhinged energy, uses slang ("Cooked", "Apeing"), distinct purple text bubbles.

## [v7.1] - The "Vitalik & Atmosphere" Update 🦄
* **New Character: VITALIK:** Added the "Crypto Monk" archetype.
    * **Physics:** Custom scaling (`0.92`) to reflect a slender build.
* **Weather Engine:** Implemented `numpy` linear interpolation for smooth weather transitions (Clear -> Rain -> Snow cycles).