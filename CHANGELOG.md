# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Latest Version:** v3.5
> **Release Date:** 2026-01-09

## [v3.5] - The "Alive" Update 🚶‍♂️

This major update brings the scene to life with full movement logic and deeper AI personalities.

### 🚀 New Features
* **Cinematic Entrance System**:
    * Guests now spawn off-screen (`x: -400`) and walk to the barrel (`x: 550`).
    * Implemented `create_walk_scene()` function handling both Intro and Outro.
* **Dual-Frame Animation**:
    * Engine now supports `walk_1` and `walk_2` sprites, alternating them every 5 frames for realistic leg movement.
* **Anti-Squash Logic**:
    * Added `normalize_size()` function. It creates a unified transparent canvas for sprites of varying widths, fixing the issue where characters would "shrink" or "expand" while walking.
* **Personality v2**:
    * Overhauled `SYSTEM_PROMPT`.
    * **Elon**: Now uses specific vocabulary ("First principles", "Mars") and stutters ("Uhh...").
    * **Hobo**: Uses more aggressive crypto-slang.

### 🐛 Bug Fixes
* Fixed `MoviePy Error: ImageSequenceClip requires all images to be the same size` by implementing dynamic canvas resizing.
* Fixed floating speech bubbles by recalibrating `offset_x` coordinates for the new guest position.

---

## [v3.3] - Stable UI & Anchors ⚓

Focus on visual stability and dialogue rendering.

### Added
* **Bi-Directional Anchors**: Logic to automatically flip speech bubble tails based on speaker position (Left vs Right).
* **Color Themes**:
    * **Hobo**: Brown/Orange theme (`#3e2723`).
    * **Guest**: Dark/Blue theme (`#212121`).

---

## [v2.0] - The Pivot 🛢️

Complete conceptual overhaul from "AlphaBits" to "BarrelDAO".

### Changed
* **Setting**: Replaced "Newsroom" background with "Dark Alleyway".
* **Cast**: Replaced "Cat & Robot" with "Hobo & Elite Guests".
* **Audio**: Updated beep tones to match gritty atmosphere.

---

## [v1.0] - Genesis

* Initial Python script (`run_pixel.py`) deployment.
* Basic OpenAI integration.