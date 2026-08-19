<img width="1460" height="798" alt="Screenshot 2026-08-20 at 2 54 33 AM" src="https://github.com/user-attachments/assets/2aba47b9-d326-4f20-b62c-ca2f90905ba8" />
# 🎮 Doofus Adventure Game — Hitwicket 2026 Challenge

An interactive 3D platformer developed in **Unity (C#)** for the **Hitwicket Game Developer Challenge** (`HW_2026_Test`). Control **Doofus** as he navigates across disappearing green platforms (Pulpits). Each platform has an active countdown timer; move quickly to newly spawned adjacent platforms before the current one collapses underneath[cite: 1]!

---

## 📺 Gameplay Demonstration

[![Doofus Adventure Gameplay Demo](https://img.youtube.com/vi/Qn_9yp-fPhs/maxresdefault.jpg)](https://www.youtube.com/watch?v=Qn_9yp-fPhs)

> 🔗 **[Click here to watch the full gameplay recording on YouTube](https://www.youtube.com/watch?v=Qn_9yp-fPhs)**[cite: 1]

---

## 📸 Screenshots

| Start Screen | Active Gameplay (Platform Timer) |
| :---: | :---: |
| ![Start Menu](<img width="1460" height="798" alt="Screenshot 2026-08-20 at 2 54 33 AM" src="https://github.com/user-attachments/assets/2dd1537a-f357-41f1-aee2-89298eca7258" />
) | ![Gameplay Countdown](Media/gameplay_1.png) |
| **Score Progression** | **Game Over Screen** |
| ![Score Progression](Media/gameplay_2.png) | ![Game Over](Media/game_over.png) |

---

## 🏆 Levels & Features Implemented

### **Level 1: Character Movement, Dynamic Pulpits & JSON Loader**[cite: 1]
* **Dynamic JSON Configuration:** Reads movement speed, pulpit min/max lifespan, and spawn intervals dynamically from `Assets/StreamingAssets/doofus_diary.json` at runtime[cite: 1].
* **Responsive 3D Controls:** Smooth physics-based 4-directional player movement mapped to WASD and Arrow Keys[cite: 1].
* **Strict "Max 2 Pulpits" Spawning:** Spawns 9x9 metallic green platforms adjacent to the previous platform, ensuring no more than two active pulpits exist on-screen at any time[cite: 1].
* **Real-Time Countdown Display:** Live world-space timers projected onto each platform indicating remaining time before despawn[cite: 1].
* **Fall Detection:** Triggers an immediate game-over state if Doofus walks off an edge or if a platform despawns underneath[cite: 1].

### **Level 2: Pulpit Traversal & Score Tracking**[cite: 1]
* **Unique Visit Validation:** Trigger-based platform detection ensuring score increments by 1 only upon successfully reaching a new pulpit[cite: 1].
* **High Score Persistence:** Live HUD score tracking combined with high-score tracking across play sessions.

### **Level 3: Full UI Loop & State Management**[cite: 1]
* **Start Screen:** Custom animated menu featuring a "Start Game" action and high score display[cite: 1].
* **In-Game HUD:** Minimalist, high-visibility score counter and real-time pulpit timer overlays[cite: 1].
* **Game Over Screen:** Clean end-game screen with "Play Again" (instant state reset) and "Exit" capabilities[cite: 1].

---

## 🕹️ Controls

| Input Key | Direction / Action |
| :--- | :--- |
| `W` / `Up Arrow` | Move Forward[cite: 1] |
| `S` / `Down Arrow` | Move Backward[cite: 1] |
| `A` / `Left Arrow` | Move Left[cite: 1] |
| `D` / `Right Arrow` | Move Right[cite: 1] |

---

## ⚙️ Configuration (`doofus_diary.json`)

All key game balancing values are loaded dynamically from `Assets/StreamingAssets/doofus_diary.json`[cite: 1]:

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
