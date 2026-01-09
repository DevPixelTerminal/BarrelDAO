# 📜 BarrelDAO Change Log

All notable changes to the "Night Shift Terminal" engine will be documented in this file.

> **Latest Version:** v5.0
> **Release Date:** 2026-01-09

## [v5.0] - The "Newsroom" Update 📰

We have achieved autonomy. The engine now selects its own topics and manages multiple guests sequentially.

### 🚀 New Features
* **Auto-News Generator (`get_auto_topic`)**:
    * Replaced manual `input()` with an AI agent that scans character interests.
    * Defined `TOPIC_INTERESTS` for each character (e.g., Elon likes "Mars", Don likes "The Wall").
    * Generates satirical headlines on the fly.
* **Sequential Episode Logic**:
    * Refactored `main()` loop to support a playlist format (Act 1 -> Act 2).
    * Guests now enter, converse, and leave one by one.
* **New Character: DON**:
    * Added full asset support (Idle, Talk, Blink, Walk 1/2).
    * Added unique "Red Tie" UI theme (`#b71c1c`).
    * Added unique personality prompt ("Loud", "Huge", "Fake News").
* **Code Refactoring**:
    * Moved from hardcoded variables to a scalable `ASSETS` dictionary.
    * Simplified audio/visual pipelines to read directly from the dictionary.

---

## [v3.5] - The "Alive" Update 🚶‍♂️

This major update brought the scene to life with full movement logic.

### Added
* **Cinematic Entrance System**: Guests spawn off-screen and walk to the barrel.
* **Dual-Frame Animation**: Support for `walk_1` and `walk_2` sprites.
* **Anti-Squash Logic**: Algorithm to normalize sprite canvas size during movement.

---

## [v3.3] - Stable UI & Anchors ⚓

Focus on visual stability and dialogue rendering.

### Added
* **Bi-Directional Anchors**: Speech bubbles automatically flip based on speaker position.
* **Color Themes**: Distinct UI colors for Host vs Guest.

---

## [v2.0] - The Pivot 🛢️

Complete conceptual overhaul from "AlphaBits" to "BarrelDAO".

### Changed
* **Setting**: Dark Alleyway background.
* **Cast**: Hobo & Elite Guests.

---

## [v1.0] - Genesis

* Initial Python script deployment.