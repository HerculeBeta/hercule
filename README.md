# Hercule Client

A high-performance, private utility and modification client for Minecraft on Windows.

![Minecraft](https://img.shields.io/badge/Minecraft-v1.21.132-green.svg)
![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-lightgrey.svg)
![Source](https://img.shields.io/badge/Source-Proprietary-red.svg)

---

## 🚀 Download

<p align="center">
  <a href="https://hercule.solisdev.xyz">
    <img src="https://img.shields.io/badge/DOWNLOAD%20LAUNCHER-HERCULE%20CLIENT-00c853?style=for-the-badge&logo=windows&logoColor=white" alt="Download Hercule Client"/>
  </a>
</p>

---

## Overview

Hercule is a modular native C++ utility client designed specifically for Minecraft on Windows platforms. Engineered to prioritize performance and stability, Hercule offers an extensible workspace featuring over 120 built-in modules, a robust Lua 5.4 scripting engine, and a fully customizable Heads-Up Display (HUD) editor.

> ⚠️ **Important**
>
> Hercule is a proprietary, closed-source project. This repository serves as the official documentation hub, issue tracker, and community Lua script sharing space. No source code or authorization mechanisms are hosted here.

---

## Key Features

- **DirectX Rendering Pipeline**  
  Direct hooks into the rendering engine minimize CPU and GPU overhead, preserving stable frame rates during intensive usage.

- **Interactive HUD Editor**  
  Press <kbd>Right Shift</kbd> to access the layout editor. Supports real-time scaling, snapping, and grouping of visual overlays.

- **Lua 5.4 Scripting VM**  
  Extend the client dynamically with custom scripts without restarting the game.

- **Developer Console**  
  Press <kbd>F4</kbd> for a fast in-game command terminal.

---

## Feature Categories

| Category | Description | Key Modules |
|----------|------------|-------------|
| **Combat** | Target filtering and optimization | Killaura, TriggerBot, AutoWeapon |
| **Movement** | Traversing the environment | Flight, Velocity Control, Step |
| **Visual** | Spatial awareness and tracking | BlockESP, StorageESP, Nametags |
| **World** | Automated block interaction | Scaffold, Nuker, Auto-Farming |
| **Player** | Inventory automation | Auto-Armor, MLG, Auto-Tool |
| **Misc** | Utility tools | Command Terminal, Discord RPC |

---

## Directory Structure

```
Documents/
└── Hercule/
    └── Client/
        ├── Assets/
        │   └── Textures/
        ├── Scripts/
        └── default.hercule
```

---

## Lua Scripting API

<details>
<summary><b>Click to expand Lua example</b></summary>

```lua
local CustomFly = {}

module.register("CustomFly", "Basic movement example", "Movement", CustomFly)
module.addSlider("CustomFly", "Speed", "Velocity multiplier", 0.5, 5.0, 1.5)

function CustomFly.on_disable(self)
    player.setMotion(0, 0, 0)
end

function CustomFly.on_tick(self)
    local speed = module.get("CustomFly", "Speed")
    local moveForward = client.isKeyDown("w")

    if moveForward then
        local yaw = player.getRot()
        local rad = math.rad(yaw + 90)
        player.setMotion(math.cos(rad) * speed, 0, math.sin(rad) * speed)
    end
end
```

</details>

---

## ⚠️ Disclaimer

This software is intended strictly for educational, offline, and private single-player testing purposes.

- No responsibility for bans or account actions
- No redistribution of compiled binaries allowed
- Use at your own risk
