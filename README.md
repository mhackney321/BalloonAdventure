# BalloonAdventure

# 🎈 Balloon Adventure

A whimsical iOS game where you navigate a hot air balloon through increasingly challenging skies filled with obstacles, weather effects, and power-ups.

Built with **Swift**, **SwiftUI**, and **SpriteKit**.

![iOS 16.0+](https://img.shields.io/badge/iOS-16.0%2B-blue)
![Swift 5.9](https://img.shields.io/badge/Swift-5.9-orange)
---

## 🎮 Gameplay

Tap the screen to make your balloon rise and navigate through the sky. Avoid obstacles, collect power-ups, and complete levels to unlock new challenges with different weather conditions.

**Controls:**
- **Tap** — Give the balloon a burst of lift
- **Hold** — Continuous upward force
- **Release** — Let gravity pull you down

---

## ✨ Features

### 🌤️ Dynamic Weather System
Each level features unique weather that affects gameplay:

| Weather | Effect |
|---------|--------|
| ☀️ Clear | Perfect flying conditions |
| 🌧️ Rain | Balloon becomes heavier, falls faster |
| ❄️ Snow | Sideways drift makes control tricky |
| 💨 Wind | Strong gusts push you off course |

### 🚧 Obstacles
Navigate around 5 different obstacle types:
- 🐦 **Birds** — Small and fast
- 🚁 **Drones** — Hover in place
- 🚧 **Barriers** — Static obstacles
- ⛈️ **Storm Clouds** — Large danger zones
- ✈️ **Airplanes** — Fast and deadly

### ⚡ Power-Ups
Collect power-ups to gain temporary advantages:

| Power-Up | Duration | Effect |
|----------|----------|--------|
| 💨 Wind Gust | 3s | Speed boost |
| 🛡️ Bubble Shield | 5s | Invincibility |
| ⏱️ Slow Motion | 4s | Slows obstacles |
| ⬆️ Extra Lift | 2s | Enhanced buoyancy |

### 🏆 Progression System
- **10 Levels** with increasing difficulty
- **Achievements** to unlock
- **Local Leaderboard** to track your best scores
- **Persistent Progress** saved automatically

---

## 📱 Screenshots

<p align="center">
  ![Balloon Adventure Menu](Menu.png)
  ![Balloon Adventure Gameplay](GamePlay.png)
  ![Balloon Adventure GameOver](GameOver.png)
  ![Balloon Adventure Level-Select](Level-Select.png)
</p>

```
screenshots/
├── menu.png
├── gameplay.png
├── level-select.png
└── game-over.png
```

---

## 🛠️ Installation

### Requirements
- macOS Sonoma 14.0+ or Ventura 13.5+
- Xcode 15.0+
- iOS 16.0+ (device or simulator)

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/BalloonAdventure.git
   cd BalloonAdventure
   ```

2. **Open in Xcode**
   ```bash
   open BalloonAdventure.xcodeproj
   ```

3. **Select a simulator or device**
   - Choose an iPhone from the device dropdown (e.g., iPhone 15)

4. **Build and run**
   - Press `Cmd + R` or click the Play button

### Troubleshooting

**"Signing requires a development team"**
1. Select the project in the navigator
2. Go to **Signing & Capabilities**
3. Choose your Apple ID from the Team dropdown

**Build errors**
- Clean build folder: `Cmd + Shift + K`
- Rebuild: `Cmd + R`

---

## 📁 Project Structure

```
BalloonAdventure/
├── BalloonAdventureApp.swift      # App entry point
├── Views/
│   ├── ContentView.swift          # Main menu with animated balloon
│   ├── GameContainerView.swift    # Game screen with HUD overlay
│   └── MenuViews.swift            # Settings, Leaderboard, Achievements, Level Select
├── Game/
│   ├── GameScene.swift            # SpriteKit game logic & physics
│   └── ParticleEmitters.swift     # Weather & effect particles
├── Managers/
│   ├── GameManager.swift          # Game state & persistence
│   └── AudioManager.swift         # Sound effects & haptics
└── Utilities/
    └── Extensions.swift           # Helper extensions
```

---

## 🏗️ Architecture

| Component | Responsibility |
|-----------|---------------|
| **GameScene** | SpriteKit scene handling physics, collisions, spawning |
| **GameManager** | Singleton managing game state, scores, achievements, persistence |
| **AudioManager** | Sound effects and haptic feedback |
| **GameContainerView** | SwiftUI wrapper bridging SpriteKit with SwiftUI HUD |

### Key Design Decisions

- **SwiftUI + SpriteKit Hybrid** — SwiftUI for menus and HUD, SpriteKit for performant game physics
- **Singleton GameManager** — Centralized state accessible from both SwiftUI and SpriteKit
- **Protocol-based Communication** — `GameSceneDelegate` cleanly separates game events from UI updates
- **UserDefaults Persistence** — Simple, reliable local storage for scores and progress

---

## 🎯 Game Configuration

Levels are defined in `GameManager.swift` via `LevelConfig`:

```swift
LevelConfig(
    level: 1,
    targetScore: 100,
    obstacleSpeed: 150,
    obstacleFrequency: 2.0,
    powerUpFrequency: 8.0,
    weather: .clear,
    enabledObstacles: [.bird, .barrier],
    enabledPowerUps: [.extraLift, .bubbleShield],
    backgroundTheme: .daySky
)
```

Customize difficulty by adjusting:
- `obstacleSpeed` — How fast obstacles move
- `obstacleFrequency` — Seconds between obstacle spawns
- `powerUpFrequency` — Seconds between power-up spawns
- `enabledObstacles` — Which obstacle types appear
- `weather` — Weather effect for the level

---

## 🔮 Future Enhancements

- [ ] Game Center integration for global leaderboards
- [ ] iCloud sync for cross-device progress
- [ ] Additional levels and worlds
- [ ] New obstacle and power-up types
- [ ] Customizable balloon skins
- [ ] Daily challenges
- [ ] Sound effects and background music

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Copyright (c) 2025 Marcus Hackney

---

## 👨‍💻 Author

**Marcus Hackney**

- GitHub: [@mhackney321]
---

<p align="center">
  Made with ❤️ and Swift
</p>

<p align="center">
  🎈 Happy Flying! 🎈
</p>
