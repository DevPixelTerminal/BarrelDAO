# 🛢️ BarrelDAO: Night Shift Terminal (v6.4)

> **Status:** Autonomous | **Uptime:** 24/7 | **Vibe:** Bear Market Apocalyptic

**BarrelDAO** is a fully autonomous, generative pixel-art sitcom engine. It simulates a late-night talk show in a dirty alleyway, hosted by a crypto-homeless sage. The engine combines **LLM-driven improv comedy** with **retro 32-bit aesthetics** to create endless content about the absurdity of modern economics, tech, and politics.

---

## 🎭 The Cast (Personality & Assets)

The engine currently supports a robust roster of AI agents, each with unique visual behaviors and prompt-engineered speech patterns.

### 🏠 The Host (Resident)
#### 🔥 HOBO (The Oracle)
* **Archetype:** The Fallen Trader.
* **Backstory:** Lost his life savings in the FTX crash. Now lives in a barrel, burning fiat currency for warmth. He is cynical, grounded, and the only one who sees reality clearly.
* **Visuals:** Dirty coat, fingerless gloves.
* **AI Logic:** Responds with dark humor and market metaphors (e.g., "My net worth is currently stable at zero").

### ⭐️ The Guests (Rotation)

#### 🚀 ELON (The Tech King)
* **Archetype:** Visionary / Meme Lord.
* **Behaviors:** Stutters when excited. Obsessed with "First Principles", Mars colonization, and DOGE ticker price.
* **Physics:** Standard movement.
* **Key Topics:** Rockets exploding, AI safety, X (Twitter) drama.

#### 🦅 DON (The Tycoon)
* **Archetype:** The Populist Dealmaker.
* **Behaviors:** Loud, aggressive, hand-accordion gestures. Uses superlatives ("HUGE", "DISASTER").
* **Visuals:** Oversized red tie, blue suit.
* **AI Logic:** Focuses on "The Wall", "China", and personal grievances.

#### ⚡ TOLY (The Builder)
* **Archetype:** The High-Speed Engineer.
* **Behaviors:** Intense, practical. Speaks in technical jargon about "Throughput" and "Latency".
* **Quote:** "Building a startup is like chewing glass."
* **Special Logic:** Uses custom scale settings (`0.85`) to match the sprite style.

#### 🕶️ TATE (The Top G)
* **Archetype:** The Matrix Breaker.
* **Behaviors:** Arrogant, alpha-posturing. Smokes a cigar constantly. Calls everyone "Brokies".
* **Visuals:** Bald, sunglasses, muscle fit tee.
* **Unique Physics (`Cigar Engine`):**
    * Uses a custom `BLINK_LEN` of **15 frames** (instead of standard 3) to simulate a long, slow drag from his cigar.
    * Uses the `OFFSETS` system to synchronize body position between smoking and talking.

---

## ⚙️ Engine Mechanics (Under the Hood)

### 1. Autonomous News Aggregator
The system needs no human input.
* **Input:** The engine checks the `TOPIC_INTERESTS` of the current guest.
* **Process:** GPT-4o generates a satirical "Breaking News" headline based on those interests.
* **Output:** "Bitcoin crashes because CEO forgot password" (Example).

### 2. The "Offset-Sync" Render Pipeline (v6.4)
Pixel art often breaks when characters perform complex actions (like smoking or raising hands), changing the sprite's center of mass.
* **Problem:** Center-alignment causes the character to "jump" left or right when the sprite width changes.
* **Solution:** We implemented a granular `OFFSETS` dictionary. We can manually shift the character on the X-axis for *each specific state* (Idle, Talk, Blink) to ensure they stay perfectly planted on the ground.

### 3. Dynamic "Ping-Pong" Atmosphere
Static backgrounds are boring. We use a **4-frame loop pattern (`0-1-2-3-2-1`)** to create a smooth, flickering fire effect in the barrel, giving the scene life without consuming excessive rendering resources.

---

## 🛠 Configuration Guide

To tweak characters, edit the `ASSETS` dictionary in `run_pixel.py`.

**v6.4 Update:** We now use an `OFFSETS` dictionary for precise alignment.

```python
"CHAR_NAME": {
    "SCALE": 1.0,          # Size multiplier (1.0 = 700px height)
    "OFFSET_Y": 0,         # Vertical shift (Fixes floating feet)
    "BLINK_LEN": 3,        # Duration of blink (3 = Fast, 15 = Long Drag)
    
    # Manual Alignment Fix (X-Axis)
    # Allows shifting specific states if the sprite width causes jumping.
    "OFFSETS": {
        "IDLE": -50,   # Shift LEFT when silent
        "TALK": 0,     # Anchor point (Talking)
        "BLINK": -50   # Shift LEFT when smoking
    }
}