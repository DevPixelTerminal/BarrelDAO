# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Latest Version:** v6.3
> **Release Date:** 2026-01-10

## [v6.3] - The "Top G" Update 🕶️💨

Added the fourth guest character: **Andrew (TATE)** and advanced animation physics.

### 🚀 New Features
* **New Character Integrated: TATE**:
    * Added full asset support (`andrew`, `andrew_talk`, `andrew_smoke`, `andrew_walk`).
    * Configured "Top G" UI theme (Black BG / Gold Border).
    * **Personality Engine**: Prompts focused on "Matrix", "Sparkling Water", and calling people "Brokies".
* **Cigar Physics Engine (`BLINK_LEN`)**:
    * Implemented variable blink duration. Tate now takes a long drag from his cigar (15 frames) instead of a standard blink (3 frames).
* **Smart Alignment System (`TALK_OFFSET_X`)**:
    * Added manual offset correction to fix characters shifting sideways during talking animations due to sprite width differences (e.g., when raising a hand or cigar).

## [v6.0] - The "Stable Scale" Update 📐

Major overhaul of the rendering pipeline.

### 🐛 Bug Fixes
* **Auto-Crop Removal**: Removed the unstable auto-cropping logic that caused characters to shrink/grow unpredictably.
* **Smart Scaling**: The engine now calculates the zoom factor based *only* on the IDLE sprite and applies it consistently to all other animations (Talk/Walk), preventing size jittering.

---

## [v5.6] - The "Optimization" Update ⚡

Added the third guest character: **Anatoly (TOLY)**.

### 🚀 New Features
* **New Character Integrated: TOLY**:
    * Configured Solana-themed UI colors (Purple BG / Green Border).
    * **Personality Engine**: Added specific prompts for "Chewing Glass" metaphors and technical jargon about throughput.
* **Expanded Playlist**:
    * Main loop now runs sequentially: Elon -> Toly -> Don -> Tate.

---

## [v5.0] - The "Newsroom" Update 📰

We have achieved autonomy. The engine now selects its own topics.

### 🚀 New Features
* **Auto-News Generator**: AI agent scans character interests and generates satirical headlines on the fly.