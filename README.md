# 🎮 Doofus Adventure Game — Hitwicket 2026 Challenge

An interactive 3D arcade platformer built in **Unity 6 (C#)** for the **Hitwicket Game Developer Challenge** (`HW_2026_Test`). Guide **Doofus** across decaying green platforms (Pulpits) that disappear within seconds, maintaining balance and quick reflexes across dynamically spawning paths.

---

## 📺 Gameplay Demonstration

[![Doofus Adventure Gameplay Demo](https://img.youtube.com/vi/Qn_9yp-fPhs/maxresdefault.jpg)](https://www.youtube.com/watch?v=Qn_9yp-fPhs)

> 🔗 **[Click here to watch the full gameplay recording on YouTube](https://www.youtube.com/watch?v=Qn_9yp-fPhs)**[cite: 1]

---

## 📸 Screenshots

| Start Screen | Gameplay & Countdown Timers | Game Over Screen |
| :---: | :---: | :---: |
| ![Start Screen](Media/start_screen.png) | ![Active Gameplay](Media/gameplay.png) | ![Game Over](Media/game_over.png) |

---

## 🏆 Levels & Features Implemented

### **Level 1: Character Movement, Dynamic Platforms & JSON Integration**[cite: 1]
* **Smooth Physics-Based Movement:** Fully responsive 4-directional player movement mapped to WASD and Arrow Keys[cite: 1].
* **Dynamic JSON Configuration:** Reads gameplay variables (Doofus movement speed, pulpit min/max lifespan, and spawn intervals) dynamically from `StreamingAssets/doofus_diary.json` at runtime[cite: 1].
* **Strict Max 2 Pulpits Rule:** Spawns random 9x9 metallic green platforms adjacent to the current platform, strictly maintaining at most 2 platforms active simultaneously[cite: 1].
* **Dynamic Countdown HUD:** Each platform displays a real-time 3D countdown timer indicating remaining lifetime before destruction[cite: 1].
* **Fall Detection:** Game automatically detects when Doofus falls off platform edges or into the abyss when a platform despawns[cite: 1].

### **Level 2: Platform Traversal & Scoring System**[cite: 1]
* **Unique Visit Validation:** Tracks individual platform IDs using trigger zones so Doofus only gains score points upon successfully transitioning to a new platform[cite: 1].
* **Real-time HUD Updates:** In-game score increments instantly as you navigate from platform to platform[cite: 1].

### **Level 3: Complete Game Loop & UI System**[cite: 1]
* **Start Menu:** Clean title screen with a "Start Game" transition[cite: 1].
* **In-Game HUD:** Displays live score counter and smooth camera tracking[cite: 1].
* **Game Over Screen:** Triggers upon falling off the edge, displaying the final score and a seamless "Restart" button that resets the gameplay state[cite: 1].

---

## 🎮 Controls

| Key / Input | Action |
| :--- | :--- |
| `W` / `Up Arrow` | Move Forward[cite: 1] |
| `S` / `Down Arrow` | Move Backward[cite: 1] |
| `A` / `Left Arrow` | Move Left[cite: 1] |
| `D` / `Right Arrow` | Move Right[cite: 1] |

---

## ⚙️ Configuration (`doofus_diary.json`)

The game fetches all core balancing attributes from `Assets/StreamingAssets/doofus_diary.json`[cite: 1]:

```json
{
  "player_data": {
    "speed": 5.5
  },
  "pulpit_data": {
    "min_pulpit_destroy_time": 4.0,
    "max_pulpit_destroy_time": 6.0,
    "pulpit_spawn_time": 2.5
  }
}
