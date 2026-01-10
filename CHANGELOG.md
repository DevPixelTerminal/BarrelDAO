# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Current Version:** v6.3
> **Release Date:** 2026-01-10

---

## [v6.3] - The "Top G" Update 🕶️💨
**Major Content & Physics Update.**
Added Andrew Tate and implemented complex animation logic to support non-standard gestures (smoking).

### 🚀 New Features
* **New Character: ANDREW (TATE)**
    * Integrated "Top G" persona: obsessed with The Matrix, Bugattis, and Sparkling Water.
    * Added specific assets: `andrew.png` (Idle), `andrew_talk.png` (Talk), `andrew_smoke.png` (Action).
    * **UI Theme:** Black background with Gold borders (#FFD700).
* **Cigar Physics Engine (`BLINK_LEN`)**
    * The engine now supports variable blink durations.
    * **Logic:** Standard characters blink for 3 frames. Tate takes a drag from his cigar for **15 frames**.
    * This allows for "Action Idle" animations (drinking, smoking, looking at phone) without changing the core loop.
* **Smart Alignment System (`TALK_OFFSET_X`)**
    * **Problem:** When Tate raised his hand to smoke, the sprite width doubled, causing his body to "jump" to the left due to center alignment.
    * **Solution:** Implemented a manual offset variable. We now push the sprite +45px on the X-axis during the `TALK` state to keep the body perfectly still.

### 🐛 Bug Fixes
* **Playlist Logic**: Enabled all guests in the main loop. The show now runs sequentially: Elon -> Toly -> Don -> Tate.

---

## [v6.1] - The "Smart Fix" Update 🧠
**Rendering Core Overhaul.**

### 🐛 Bug Fixes
* **Fixed "Jumping Size" Glitch**: Characters no longer change size when blinking or talking.
    * **Solution:** The engine now calculates the `zoom_factor` based *only* on the IDLE sprite dimensions and applies that exact factor to all other sprites, regardless of their crop size.
* **Fixed "Floating Feet"**: Replaced Center-Bottom alignment with Left-Bottom (Spine-based) alignment for better stability.

---

## [v6.0] - Stable Release 🛡️
**Critical Rollback.**
* Removed the experimental `Auto-Crop` feature which was accidentally cutting off character limbs.
* Reverted to "Canvas Trust" logic: The engine now trusts that the input PNGs are correctly framed by the artist.

---

## [v5.6] - The "Optimization" Update ⚡
Added Solana integration and rendering speedups.

### 🚀 New Features
* **New Character: TOLY (Solana)**
    * Added `toly_idle`, `toly_talk`, `toly_walk` assets.
    * Persona prompt: "High throughput, chewing glass, hates gas fees."
    * **Manual Scale**: Implemented specific scaling (`SCALE: 0.85`) for characters with unique proportions.
* **Fast Mode Rendering**:
    * Switched `moviepy` preset to `ultrafast`.
    * Reduced framerate to **12 FPS** (matches pixel art style better and renders 2x faster).
    * Enabled Multi-threading (4 threads).

---

## [v5.0] - The "Newsroom" Update 📰
**AI Autonomy Milestone.**

### 🚀 New Features
* **Auto-Topic Generator**:
    * The script now queries GPT-4o to invent a news headline based on the guest's interests before generating dialogue.
    * Eliminated manual input prompts.
* **New Character: DON (Trump)**
    * Integrated assets with the iconic red tie and "MAGA" speech patterns.

---

## [v1.0 - v4.0] - The Foundation 🏗️
* **v3.5**: Added Cinematic Walk-In/Walk-Out sequences.
* **v2.0**: Rebranding to "BarrelDAO".
* **v1.0**: Initial Python script deployment.