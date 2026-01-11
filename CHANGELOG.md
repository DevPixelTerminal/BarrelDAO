# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Current Version:** v7.2
> **Release Date:** 2026-01-11

---

## [v7.2] - The "We Are So Back" Update 📈
**Roster Expansion & Animation Upgrade.**
Injected pure "Crypto Twitter" chaos into the simulation. Added the first streamer archetype to contrast with the billionaires and builders.

### 🧢 New Character: THREADGUY
* **Added `THREADGUY` to the roster.**
    * **Archetype:** The "Degen Streamer". Represents the manic highs and lows of the market.
    * **Visuals:** Highly detailed 32-bit sprite featuring the iconic white zip-up hoodie (with purple Twitch logo), messy "broccoli" hair, and grey sweatpants.
    * **Persona:** Unhinged, loud, and emotional. Uses specific internet slang ("I am cooked", "It is over", "We are so back", "Apeing").
    * **Audio:** Custom 8-bit voice pitch-shifted to match his energetic speaking style.
    * **Assets:** Full integration of `WALK`, `WALK_2` (scissor-step logic), `TALK`, and `BLINK` sprites.

### 🎨 Visual Polish
* **Twitch Aesthetic:** Implemented a new custom text bubble color scheme (`#6441a5` Background) specifically for ThreadGuy to match his branding.

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