# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Latest Version:** v5.6
> **Release Date:** 2026-01-10

## [v5.6] - The "Optimization" Update ⚡

Added the third guest character: **Anatoly (TOLY)**.

### 🚀 New Features
* **New Character Integrated: TOLY**:
    * Added full asset support (`toly_idle`, `toly_talk`, `toly_walk_1`, `toly_walk_2`).
    * Configured Solana-themed UI colors (Purple BG / Green Border).
    * **Personality Engine**: Added specific prompts for "Chewing Glass" metaphors and technical jargon about throughput and latency.
* **Expanded Playlist**:
    * Main loop now runs 3 episodes sequentially: Elon -> Toly -> Don.

## [v5.2] - The "Atmosphere" Update 🔥

Focus on visual immersion and dynamic backgrounds.

### 🚀 New Features
* **Animated Background Engine**:
    * Replaced static `BG_IMAGE` with a `BG_FILES` array supporting multiple frames (JPEG/PNG).
    * Implemented `create_flickering_bg()` function using a "Ping-Pong" loop pattern (`[0, 1, 2, 3, 2, 1]`) for smooth, non-repetitive fire animation.

## [v5.1] - Visual Stability Fixes 📐

Critical hotfix for UI rendering.

### 🐛 Bug Fixes
* **Text Overflow Fix**:
    * Rewrote `get_text_dimensions_robust()` to calculate exact pixel width of text strings instead of estimating via character count.
    * Added "Safety Padding" (+25px) to speech bubbles to prevent text clipping on the right edge.

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

## [v1.0] - Genesis

* Initial Python script deployment.