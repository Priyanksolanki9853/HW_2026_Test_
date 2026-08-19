<div align="center">

# 🎲 DOOFUS ADVENTURE GAME 🎲

### *One wrong step and the floor is gone.*

![Unity](https://img.shields.io/badge/Engine-Unity%206-black?style=for-the-badge&logo=unity)
![C#](https://img.shields.io/badge/Language-C%23-239120?style=for-the-badge&logo=csharp)
![Platform](https://img.shields.io/badge/Platform-PC-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

**A minimalist 3D survival-platformer built for the Hitwicket Game Developer Challenge.**
Outrun the collapse. Chase the high score. Don't look down.

[▶️ Watch Gameplay](#-gameplay-demo) • [📸 Screenshots](#-screenshots) • [✨ Features](#-features) • [⌨️ Controls](#️-controls) • [🚀 Setup](#-run-it-yourself)

</div>

<br>

## 🧩 What Is This?

**Doofus** is stranded on a floating pulpit — a small platform with a ticking clock. The moment it expires, it's gone, and so is Doofus if he's still standing on it. A fresh pulpit spawns beside the old one, but only ever **two exist at once**. Your only move is forward: hop, survive, repeat.

No health bars. No enemies. Just timing, nerve, and a shrinking world beneath your feet.

<br>

## 📺 Gameplay Demo

<div align="center">

[![Watch the gameplay recording](https://img.youtube.com/vi/Qn_9yp-fPhs/maxresdefault.jpg)](https://www.youtube.com/watch?v=Qn_9yp-fPhs)

**🎬 [Click to watch the full playthrough on YouTube →](https://www.youtube.com/watch?v=Qn_9yp-fPhs)**

</div>

<br>

## 📸 Screenshots

<table align="center">
<tr>
<td align="center" width="50%">
<img src="<img width="1460" height="798" alt="Screenshot 2026-08-20 at 2 54 33 AM" src="https://github.com/user-attachments/assets/4b1c9ba6-9122-4777-8fcc-c49e84e816be" />
" width="100%"><br>
<sub><b>🏠 Start Screen</b> — jump in with one click, high score always in view</sub>
</td>
<td align="center" width="50%">
<img src="Media/gameplay_1.png" width="100%"><br>
<sub><b>⏱️ The Chase Begins</b> — pulpit timer ticking, one hop scored</sub>
</td>
</tr>
<tr>
<td align="center" width="50%">
<img src="Media/gameplay_2.png" width="100%"><br>
<sub><b>🔥 Building Momentum</b> — three pulpits down, clock still running</sub>
</td>
<td align="center" width="50%">
<img src="Media/game_over.png" width="100%"><br>
<sub><b>💀 Game Over</b> — instant retry or bail, high score locked in</sub>
</td>
</tr>
</table>

<br>

## ✨ Features

### 🕹️ Movement & World
- **Data-driven design** — player speed and pulpit lifetimes are never hardcoded; everything streams in from `doofus_diary.json` at runtime.
- **Smooth 4-directional physics movement**, mapped to WASD and the arrow keys.
- **Live edge detection** — step off a platform or let one expire under you, and it's instant game over.

### 🟩 The Pulpit System
- Platforms spawn **adjacent** to the current one, in a random walkable direction.
- A strict **two-pulpit rule** — never more, never less, keeping the challenge tight and readable.
- **World-space countdown timers** rendered directly on each platform, so you always know how much time you've got left to jump.

### 🏅 Scoring & Progression
- Score increases **once per unique pulpit reached** — no cheesing it by hopping back and forth.
- **Persistent high score**, tracked across sessions and visible from the menu, the HUD, and the game-over screen.

### 🖥️ Full UI Loop
- **Start Menu** with animated play button and high score readout.
- **In-game HUD** — clean score counter + timer, nothing blocking the action.
- **Game Over screen** with one-tap **Play Again** or **Exit**.

<br>

## ⌨️ Controls

| Key | Action |
|:---:|:---|
| `W` / `↑` | Move Forward |
| `S` / `↓` | Move Backward |
| `A` / `←` | Move Left |
| `D` / `→` | Move Right |

<br>

## ⚙️ Configuration — `doofus_diary.json`

Every core balancing number lives outside the code, inside `Assets/StreamingAssets/doofus_diary.json`. Tweak it, reload, and the whole game reacts — no recompiling required.

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
```

| Key | What it controls |
|---|---|
| `speed` | Doofus's movement speed |
| `min_pulpit_destroy_time` | Shortest possible lifespan of a pulpit |
| `max_pulpit_destroy_time` | Longest possible lifespan of a pulpit |
| `pulpit_spawn_time` | Delay before the next pulpit appears |

<br>

## 🏗️ Under the Hood

| Script | Responsibility |
|---|---|
| `DataManager.cs` | Loads and parses `doofus_diary.json`, with safe fallback defaults |
| `PlayerController.cs` | Handles Doofus's movement, input, and fall detection |
| `Pulpit.cs` | Manages an individual platform's countdown, display, and trigger zone |
| `PulpitManager.cs` | Decides where the next pulpit spawns and enforces the 2-platform cap |
| `GameManager.cs` | Core state machine — Start Menu → Playing → Game Over — plus scoring |
| `UIManager.cs` | Wires up buttons, screen transitions, and live UI updates |

<br>

## 🚀 Run It Yourself

**1. Clone the repo**
```bash
git clone https://github.com/Priyanksolanki9853/HW_2026_Test.git
```

**2. Open in Unity**
Launch Unity Hub → Add project → point it at the cloned folder. Requires **Unity 6 / 2023 LTS or newer**.

**3. Hit Play**
Open `Assets/_Game/Scenes/MainScene.unity` and press ▶️ — you're on the pulpit.

<br>

<div align="center">

---

Built with 🎮 and a fair amount of falling off platforms.

**Priyank**

</div>
