# 🍥 Storm 4 Tag Team

### Naruto Shippuden: Ultimate Ninja Storm 4 — Simultaneous 3v3 Multiplayer Mod

![Development Status](https://img.shields.io/badge/Status-Research%20%26%20Development-orange)
![Platform](https://img.shields.io/badge/Platform-Windows-blue)
![Game](https://img.shields.io/badge/Game-Naruto%20Storm%204-red)
![Multiplayer](https://img.shields.io/badge/Multiplayer-3v3-purple)

**Storm 4 Tag Team** is an unofficial fan-made mod project for *Naruto Shippuden: Ultimate Ninja Storm 4*, aiming to introduce simultaneous 3v3 team battles inspired by the multi-character combat of *Naruto Shippuden: Ultimate Ninja Storm Revolution*.

The goal is to bring a new multiplayer experience to Storm 4, allowing six fighters to participate in the same battle simultaneously.

> **Project Status:** Early research and development. The features described below are planned objectives, not confirmed working implementations.

---

## 🎮 Project Overview

Unlike the traditional Storm 4 team battle system, where support characters are summoned or switched in, Storm 4 Tag Team aims to allow **all six characters to fight simultaneously**.

### Core Features

- Simultaneous 3v3 battles.
- Three active fighters per team.
- Up to six independently controlled characters.
- Local multiplayer support.
- AI-controlled teammates and opponents.
- Advanced target lock-on system.
- Dynamic team-based HUD.
- Independent health and chakra gauges.
- Improved camera tracking for multiple fighters.
- Support for mixed human and AI teams.

The project focuses exclusively on **3v3 battles**, rather than a free-for-all mode or traditional tag switching.

---

## ⚔️ 1. Simultaneous 3v3 Combat

The main objective is to expand the game's battle system to support six active fighters in one arena.

### Planned Mechanics

- Three fighters on Team A.
- Three fighters on Team B.
- All characters remain active simultaneously.
- Each fighter can move, attack, defend, and use jutsu independently.
- Characters have individual health and chakra values.
- Team members can cooperate against opponents.
- Battles end when all fighters on one team are defeated.

### Example Battle

**Team A**
- Naruto Uzumaki
- Sasuke Uchiha
- Sakura Haruno

**Team B**
- Madara Uchiha
- Obito Uchiha
- Pain

All six characters fight simultaneously without requiring character switching.

---

## 🎮 2. Local Multiplayer

The mod aims to support up to six local players.

Each human player controls a separate fighter using an assigned controller.

When fewer than six human players participate, the remaining fighters can be controlled by AI.

| Human Players | AI Fighters |
|---|---|
| 1 | 5 |
| 2 | 4 |
| 3 | 3 |
| 4 | 2 |
| 5 | 1 |
| 6 | 0 |

### Planned Controller Features

- Independent controller input.
- XInput support.
- Controller-to-character assignment.
- Configurable button mapping.
- Mixed human and AI teams.
- Individual lock-on targets.

**Technical note:** Six-controller support and simultaneous fighter control require engine research and are not yet confirmed.

---

## 🎯 3. Advanced Lock-On System

The mod will aim to introduce a new targeting system designed for 3v3 battles.

### Target Switching

Players will use the **right analog stick** to switch between enemy targets.

**Left Analog Stick**
- Character movement.

**Right Analog Stick**
- Switch between available enemy fighters.

### Example

Naruto is fighting Pain, Itachi, and Kisame.

1. Naruto initially targets Pain.
2. Move the right analog stick to the right.
3. The target changes to Itachi.
4. Move right again.
5. The target changes to Kisame.
6. Move right again to cycle back to Pain.

### Additional Features

- Visual lock-on indicator above the selected enemy.
- Camera tracking based on the current target.
- Automatic retargeting when an enemy is defeated.
- Independent targeting for each player.
- Prevention of accidental repeated target switching.
- No interference with character movement.
- Friendly characters cannot be targeted.

**Important:** Switching targets must never switch the character being controlled.

---

## 🖥️ 4. Dynamic Team-Based HUD

The original HUD will need to be redesigned to accommodate multiple active fighters.

### Planned Features

- Individual health bars.
- Individual chakra bars.
- Substitution gauges.
- Player identifiers (P1–P6).
- Team indicators.
- Defeated-character indicators.
- Automatic UI repositioning.
- Symmetrical team layouts.

### Adaptive Layout

The HUD should automatically adjust to the number of active characters.

For example:

- One fighter: centered within the team's HUD area.
- Two fighters: centered side by side.
- Three fighters: evenly distributed across the team's HUD area.

The interface should also support repositioning elements when fighters are eliminated.

### Team Layout

**Team A:** Left side of the screen.

**Team B:** Right side of the screen.

Both teams should maintain balanced and readable layouts.

---

## 🤖 5. AI-Controlled Fighters

AI fighters will fill available team slots when human players are unavailable.

### Planned AI Behavior

- Enemy target selection.
- Offensive combos.
- Defensive reactions.
- Jutsu usage.
- Substitution timing.
- Ally cooperation.
- Multiple-enemy awareness.
- Collision avoidance.
- Independent combat decisions.

The AI should behave as an active teammate or opponent rather than a temporary support character.

---

## 📷 6. Camera System

The camera must be adapted to support simultaneous combat between multiple fighters.

### Objectives

- Follow the locally controlled character.
- Prioritize the selected lock-on target.
- Dynamically adjust camera distance.
- Reduce visual obstruction.
- Maintain visibility during close-range combat.
- Handle multiple combat interactions.

Camera behavior for multiple local players will require additional investigation.

---

## 🛠️ 7. Technical Development

The project may require reverse engineering and modifications to the original game's runtime behavior.

### Research Areas

- Fighter entity management.
- Character spawning.
- Battle state management.
- Input processing.
- Controller assignment.
- Camera control.
- Combat collision systems.
- AI behavior.
- Team management.
- HUD rendering.

### Potential Development Tools

- Ghidra.
- Visual Studio.
- C/C++.
- Debugging tools.
- Binary analysis tools.
- Game asset inspection tools.

The final implementation approach will depend on verified research findings.

---

## 📂 8. Planned Repository Structure

```text
Storm-4-Tag-Team/
│
├── README.md
│
├── docs/
│   ├── roadmap.md
│   ├── architecture.md
│   └── research.md
│
├── src/
│   ├── combat/
│   ├── multiplayer/
│   ├── lock-on/
│   ├── camera/
│   ├── ai/
│   └── hud/
│
├── assets/
│   ├── hud/
│   ├── lock-on/
│   └── icons/
│
├── config/
│
├── tests/
│
└── tools/
```

This structure is provisional and will evolve as the project progresses.

---

## 🚧 9. Development Roadmap


### Phase 4 — Lock-On and Camera
- [ ] Implement target selection.
- [ ] Add right-stick target switching.
- [ ] Create lock-on indicators.
- [ ] Improve camera tracking.

### Phase 5 — User Interface
- [ ] Design the new team HUD.
- [ ] Implement individual character gauges.
- [ ] Add player indicators.
- [ ] Implement automatic HUD alignment.

### Phase 6 — Testing and Optimization
- [ ] Test battle stability.
- [ ] Test human and AI combinations.
- [ ] Fix controller conflicts.
- [ ] Optimize performance.
- [ ] Prepare an experimental build.

---

## 📦 10. Installation

No public playable release is currently available.

Installation instructions will be published once a functional experimental version has been developed.

---

## 🤝 11. Contributions

Developers, modders, reverse engineers, and Naruto Storm fans are welcome to follow the project and contribute ideas.

Potential contribution areas include:

- Reverse engineering.
- C/C++ development.
- Controller input systems.
- Gameplay programming.
- AI development.
- HUD and UI design.
- Testing and debugging.
- Technical documentation.

Please open a GitHub Issue to discuss proposed features, bugs, or research findings before submitting major changes.

---

## ⚠️ 12. Disclaimer

Storm 4 Tag Team is an unofficial fan-made modification project.

This project is not affiliated with, endorsed by, or sponsored by Bandai Namco Entertainment, CyberConnect2, or the owners of the Naruto franchise.

All related trademarks, characters, and original game assets belong to their respective owners.

This repository is intended to distribute original mod code, documentation, and independently created assets only.

It does not distribute the original game's executable or unauthorized proprietary game files.

---

### 🍥 Storm 4 Tag Team

**Three versus three. Six fighters. One battlefield. Everyone fights at once.**
## ❤️ Support Storm 4 Tag Team Development

### 🍥 Help Us Bring Simultaneous 3v3 Battles to Naruto Storm 4!

**Storm 4 Tag Team** is an independent, fan-made project dedicated to expanding *Naruto Shippuden: Ultimate Ninja Storm 4* with simultaneous 3v3 battles, improved multiplayer functionality, custom HUD elements, advanced targeting, and AI-controlled fighters.

Developing these features requires extensive research, reverse engineering, programming, testing, and countless hours of work.

**Your support can help us keep improving the project!**

### ☕ Support the Project on LivePix

If you believe in this project and would like to help its development, consider making a voluntary donation.

**❤️ [Support Storm 4 Tag Team on LivePix https://livepix.gg/revi

### 🚀 How Your Support Helps

Your contributions can help with:

- **Development:** Supporting the time and resources needed to create new features.
- **Reverse Engineering:** Researching and overcoming technical limitations in Storm 4.
- **Multiplayer Improvements:** Working toward independent controls for up to six players.
- **Bug Fixes:** Investigating crashes, improving stability, and optimizing performance.
- **Testing:** Improving compatibility across different PC configurations.
- **Future Updates:** Continuing development of the 3v3 combat system, HUD, camera, and lock-on mechanics.

### 🎮 A Free Mod for the Community

**Storm 4 Tag Team is and will remain a free fan-made mod.**

Donations are completely optional and do not grant exclusive access to gameplay features.

Even if you cannot donate, you can still support the project by starring the GitHub repository, reporting bugs, sharing feedback, and spreading the word!

### 💖 Thank You!

Every contribution, no matter how small, is appreciated.

Our goal is to create a new way to experience Naruto Storm 4 and bring the community closer to the dream of fully simultaneous 3v3 battles.

**Six Fighters. Two Teams. One Battlefield.**

*Thank you for supporting Storm 4 Tag Team!*

---

*Disclaimer: Storm 4 Tag Team is an unofficial fan project and is not affiliated with Bandai Namco Entertainment, CyberConnect2, or the Naruto franchise rights holders. Donations support independent development efforts and are not payments for the original game or its intellectual property.*
