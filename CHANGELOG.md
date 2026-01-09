# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Latest Version:** v5.2
> **Release Date:** 2026-01-10

## [v5.2] - The "Atmosphere" Update 🔥

Focus on visual immersion and dynamic backgrounds.

### 🚀 New Features
* **Animated Background Engine**:
    * Replaced static `BG_IMAGE` with a `BG_FILES` array supporting multiple frames (JPEG/PNG).
    * Implemented `create_flickering_bg()` function using a "Ping-Pong" loop pattern (`[0, 1, 2, 3, 2, 1]`) for smooth, non-repetitive fire animation.
    * Added `FRAME_HOLD` logic to control animation speed independent of video FPS.

## [v5.1] - Visual Stability Fixes 📐

Critical hotfix for UI rendering.

### 🐛 Bug Fixes
* **Text Overflow Fix**:
    * Rewrote `get_text_dimensions_robust()` to calculate exact pixel width of text strings instead of estimating via character count.
    * Added "Safety Padding" (+25px) to speech bubbles to prevent text clipping on the right edge.
    * Reduced max line width to 20 chars for better readability on mobile screens.

---

## [v5.0] - The "Newsroom" Update 📰

We have achieved autonomy. The engine now selects its own topics.

### 🚀 New Features
* **Auto-News Generator (`get_auto_topic`)**:
    * AI agent scans character interests and generates satirical headlines on the fly.
* **Sequential Episode Logic**:
    * Refactored main loop to support playlist format (Act 1 -> Act 2).
* **New Character: DON**:
    * Added full asset support and unique "Red Tie" UI theme.

---

## [v3.5] - The "Alive" Update 🚶‍♂️

### Added
* **Cinematic Entrance System**: Guests spawn off-screen and walk to the barrel.
* **Dual-Frame Animation**: Support for `walk_1` and `walk_2` sprites.
* **Anti-Squash Logic**: Algorithm to normalize sprite canvas size during movement.

---

## [v1.0] - Genesis

* Initial Python script deployment.