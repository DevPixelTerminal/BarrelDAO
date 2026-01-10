# 🛢️ BarrelDAO: Night Shift Terminal (v6.3)

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
    * Uses `TALK_OFFSET_X` to compensate for sprite width changes when raising his hand.

---

## ⚙️ Engine Mechanics (Under the Hood)

### 1. Autonomous News Aggregator
The system needs no human input.
* **Input:** The engine checks the `TOPIC_INTERESTS` of the current guest.
* **Process:** GPT-4o generates a satirical "Breaking News" headline based on those interests.
* **Output:** "Bitcoin crashes because CEO forgot password" (Example).

### 2. The "Smart-Align" Render Pipeline (v6.3)
Pixel art often breaks when characters move (e.g., raising a hand makes the image wider, shifting the body center). We solved this with a custom alignment algorithm:
* **Anchor Point:** Characters are anchored by their **Bottom-Left** pixel (the "Spine"), not the center.
* **Manual Offset (`TALK_OFFSET_X`):** A variable that forcefully pushes the character back if a specific animation frame (like Tate smoking) throws off the balance.

### 3. Dynamic "Ping-Pong" Atmosphere
Static backgrounds are boring. We use a **4-frame loop pattern (`0-1-2-3-2-1`)** to create a smooth, flickering fire effect in the barrel, giving the scene life without consuming excessive rendering resources.

---

## 🛠 Configuration Guide

To tweak characters, edit the `ASSETS` dictionary in `run_pixel.py`:

```python
"CHAR_NAME": {
    "SCALE": 1.0,          # Size multiplier (1.0 = 700px height)
    "OFFSET_Y": 0,         # Vertical shift (Fixes floating feet)
    "BLINK_LEN": 3,        # Duration of blink (3 = Fast, 15 = Long Drag)
    "TALK_OFFSET_X": 45    # Horizontal correction for wide sprites
}