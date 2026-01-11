# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Current Version:** v7.1
> **Release Date:** 2026-01-11

---

## [v7.1] - The "Vitalik & Atmosphere" Update 🦄
**Content & Immersion Upgrade.**
Added the final main cast member and overhauled the weather physics for maximum realism.

### 🎭 New Character: VITALIK
* **Added `VITALIK` to the roster.**
    * **Visuals:** Skinny sprite (`SCALE: 0.92`), unicorn t-shirt, grey sweatpants.
    * **Persona:** "The Alien Genius". Speaks in complex technical riddles (Sharding, ZK-Rollups), ignores price talk, and focuses on "Public Goods".
    * **Contrast:** Acts as a philosophical foil to the greed of Tate/Trump and the ego of Elon.

### 🌧️ Weather Engine: "Smooth Gradient"
* **Removed Block Weather:** Abandoned the binary "On/Off" weather switching.
* **Implemented Gradient Logic:** Weather now changes mathematically over **15-episode cycles** (e.g., 0% -> 5% -> 10% ... -> 100%).
* **Dynamic Particle Count:** The number of raindrops/snowflakes now scales linearly with intensity.
    * *0.1 Intensity:* Light drizzle.
    * *1.0 Intensity:* Heavy storm.
* **Wet Ground Physics:** Puddles now dry slowly (fade out opacity) after the rain stops, adding a realistic "aftermath" phase.

### 🐛 Core Fixes
* **Language Enforcer:** Hardcoded "STRICTLY ENGLISH" directives into the System Prompt to prevent the LLM from hallucinating in Russian or other languages during "Creative Mode".

---

## [v7.0] - The "Meme Lord" Update 🤡
**Major AI & Core Overhaul.**
Shifted the engine from "News Aggregation" to "Satirical Chaos". The goal is to maximize entertainment value and meme potential.

### 🧠 AI Core: "Chaos Mode"
* **Replaced Topic Logic**: Removed static interest lists. The engine now generates unique, absurd, and satirical headlines (The Onion / Pump.fun style) for every episode.
* **Adult Swim Tone**: Tuned OpenAI `temperature` to **1.15**. Characters now use slang (WAGMI, REKT, Copium), mild profanity, and aggressive roasting.
* **Deep Talk**: Increased dialogue length to **12-16 lines** for deeper, more philosophical (and delusional) debates.

### 🎨 Visual Engine: "Smart Bubbles"
* **Boundary Injection**: Implemented a mathematical "Guard Rail" system for text bubbles.
    * Logic: `if x < 20: x = 20`.
    * **Result**: Text bubbles no longer clip off-screen, regardless of how long the text is or where the character stands.
* **Stage Re-Balancing**: Moved all Guest characters significantly to the LEFT (`x=450-500` range) to improve composition and stop them from blocking the barrel.

### 🔊 Audio & System
* **AAC Codec Enforcement**: Switched audio encoding to `aac` via FFMPEG to fix silent video issues on Windows/OBS environments.
* **Local Dev Optimization**: Adjusted rendering threads for stability on local Windows machines.

---

## [v6.5] - The "Perfect Stance" Update 🧍‍♂️
**Final Physics Fix.**
Achieved perfect character stability without manual tweaking.

### 🚀 Improvements
* **Spine-Based Alignment (Left-Align)**:
    * Replaced the complex offset logic with a pure "Spine Anchor" system.
    * Characters are now anchored strictly to `x=0` (Left Edge) of their sprite.
    * **Result**: Andrew Tate no longer "jitters" or jumps sideways when transitioning between `Idle` (narrow sprite) and `Smoke` (wide sprite).
* **Code Cleanup**: Removed `TALK_OFFSET_X` and manual `OFFSETS` values from the configuration.

---

## [v6.4] - The "Offset Engine" Update 📐
**Granular Control Update.**

### 🚀 New Features
* **State-Specific Offsets**:
    * Introduced the `OFFSETS` dictionary in the config.
    * Allowed developers to manually shift `IDLE`, `TALK`, and `BLINK` states independently on the X-axis.

---

## [v6.3] - The "Top G" Update 🕶️💨
**Major Content & Physics Update.**
Added Andrew Tate and implemented complex animation logic to support non-standard gestures (smoking).

### 🚀 New Features
* **New Character: ANDREW (TATE)**
    * Integrated "Top G" persona: obsessed with The Matrix, Bugattis, and Sparkling Water.
* **Cigar Physics Engine (`BLINK_LEN`)**:
    * Logic: Tate takes a drag from his cigar for **15 frames** (vs standard 3).

---

## [v6.1] - The "Smart Fix" Update 🧠
**Rendering Core Overhaul.**

### 🐛 Bug Fixes
* **Fixed "Jumping Size" Glitch**: The engine now calculates `zoom_factor` based only on IDLE sprite dimensions.
* **Fixed "Floating Feet"**: Replaced Center-Bottom alignment with Left-Bottom alignment.

---

## [v6.0] - Stable Release 🛡️
**Critical Rollback.**
* Reverted to "Canvas Trust" logic: The engine now trusts that the input PNGs are correctly framed.

---

## [v5.6] - The "Optimization" Update ⚡
Added Solana integration and rendering speedups.

### 🚀 New Features
* **New Character: TOLY (Solana)**.
* **Fast Mode Rendering**: Switched `moviepy` preset to `ultrafast` (12 FPS).

---

## [v5.0] - The "Newsroom" Update 📰
**AI Autonomy Milestone.**

### 🚀 New Features
* **Auto-Topic Generator**: First implementation of GPT-4o headlines.
* **New Character: DON (Trump)**.