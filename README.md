# 🛢️ BarrelDAO: Night Shift Terminal (v7.0)

> **Status:** Autonomous | **Uptime:** 24/7 | **Vibe:** Adult Swim / Crypto Satire

**BarrelDAO** is a fully autonomous, generative pixel-art sitcom engine. It simulates a late-night talk show in a dirty alleyway, hosted by a crypto-homeless sage. The engine combines **LLM-driven improv comedy** with **retro 32-bit aesthetics** to create endless content about the absurdity of modern economics, tech, and politics.

---

## 🎭 The Cast (Personality & Assets)

The engine currently supports a robust roster of AI agents, each with unique visual behaviors and prompt-engineered "Meme Lord" personas.

### 🏠 The Host (Resident)
#### 🔥 HOBO (The Based Oracle)
* **Archetype:** The Fallen Trader / Diogenes.
* **Backstory:** Lost his life savings in the FTX crash. Now lives in a barrel. He is the only sane person in the room, roasting the billionaires for their delusions.
* **Visuals:** Dirty coat, fingerless gloves.

### ⭐️ The Guests (Rotation)

#### 🚀 ELON (The Meme King)
* **Archetype:** Chaotic Neutral Billionaire.
* **Personality:** Egocentric troll. Obsessed with Mars, Doge, and "saving humanity" (by charging $8 for it).
* **AI Logic:** Generates topics about buying concepts (like Gravity) or interspecies alliances.

#### 🦅 DON (The 47th)
* **Archetype:** The Populist Titan.
* **Personality:** Loud, uses CAPSLOCK. Obsessed with gold, ratings, and "winning". Thinks the Hobo is a "Low IQ individual".
* **AI Logic:** Focuses on bizarre business deals, walls, and conspiracy theories.

#### ⚡ TOLY (The Optimizer)
* **Archetype:** The Nervous Tech-Bro.
* **Personality:** Solana Founder. Denies network outages ("It's a feature"). Speaks in "TPS" and "Latency". Paradoxically anxious yet arrogant.
* **Visuals:** Hoodie, energy drink vibes.

#### 🕶️ TATE (The Top G)
* **Archetype:** The Matrix Breaker.
* **Personality:** Toxic Alpha. Smokes a cigar constantly. Calling the Hobo a "Brokie" for breathing free air.
* **Physics:** Custom **15-frame** animation loop for cigar smoking.

---

## ⚙️ Engine Mechanics (Under the Hood)

### 1. The "Chaos" Satire Engine (v7.0)
We abandoned standard news feeds for pure generative madness.
* **Step 1 (Topic):** The engine asks GPT-4o to invent a **tabloid-style headline** based on the guest's vices (Ego, Greed, Delusion).
    * *Example:* "Elon admits he is actually 3 raccoons in a trench coat."
* **Step 2 (Script):** A second AI call generates a 12-16 line script using strict "Internet Slang" parameters (WAGMI, REKT, Copium).

### 2. Smart Bubble Rendering
Text generation is unpredictable. To prevent UI glitches:
* **Boundary Injection:** The render pipeline calculates text width in real-time and mathematically forces the text bubble inside the 1280x720 canvas (`x > 10` and `y > 10`).
* **Dynamic Typing:** Uses a typewriter effect synchronized with 8-bit audio blips.

### 3. Audio & Codec Pipeline
* **Voice:** Procedural 8-bit beeping (Animal Crossing style), pitch-shifted per character.
* **Encoding:** Forces `AAC` audio codec via FFMPEG to ensure compatibility with OBS and YouTube Live streams on Windows Server environments.

---

## 🛠 Configuration Guide

To tweak characters, edit the `ASSETS` dictionary in `run_infinity.py`.

```python
"CHAR_NAME": {
    "SCALE": 1.0,          # Size multiplier
    "SPOT_X": 500,         # Horizontal Position (Left <-> Right)
    "OFFSET_Y": 0,         # Vertical shift
    
    # AI Persona Injection
    "WHO_IS_HE": "Description of the character's psyche...",
    
    # Physics
    "BLINK_LEN": 3         # 3 for blink, 15 for smoking/drinking
}