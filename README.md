# Hercule Client

A high-performance, private utility and modification client for Minecraft on Windows.

![Minecraft](https://img.shields.io/badge/Minecraft-v1.21.132-green.svg)
![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-lightgrey.svg)
![Source](https://img.shields.io/badge/Source-Proprietary-red.svg)

---

## Overview

Hercule is a modular native C++ utility client designed specifically for Minecraft on Windows platforms. Engineered to prioritize performance and stability, Hercule offers an extensible workspace featuring over 120 built-in modules, a robust Lua 5.4 scripting engine, and a fully customizable Heads-Up Display (HUD) editor.

> ⚠️ **Important**
>
> Hercule is a proprietary, closed-source project. This repository serves as the official documentation hub, issue tracker, and community Lua script sharing space. No source code or authorization mechanisms are hosted here.

---

## Download

You can download the launcher here:

:contentReference[oaicite:0]{index=0}

---

## Key Features

- **DirectX Rendering Pipeline**  
  Direct hooks into the rendering engine minimize CPU and GPU overhead, preserving stable frame rates during intensive usage.

- **Interactive HUD Editor**  
  Press <kbd>Right Shift</kbd> to access the layout editor. Supports real-time scaling, snapping, and grouping of visual overlays (e.g., coordinates, radars, armor indicators).

- **Lua 5.4 Scripting VM**  
  Extend the client dynamically. Write, compile, and load custom add-ons instantly without restarting the game or rebuilding the binary.

- **Developer Console**  
  Access a fast, searchable in-game command terminal by pressing <kbd>F4</kbd>.

---

## Feature Categories

| Category | Description | Key Modules |
|----------|------------|-------------|
| **Combat** | Target filtering and optimization | Killaura, Target Mode (Whitelist), TriggerBot, AutoWeapon |
| **Movement** | Traversing the environment | Flight, Velocity Control, Step, Custom Pathfinders |
| **Visual** | Spatial awareness and object tracking | 3D BlockESP, StorageESP, Nametags, Rotating Minimap |
| **World** | Automated block interaction | Scaffold, Nuker, Schematic Printer, Auto-Farming |
| **Player** | Inventory and state automation | InventoryManager, Auto-Armor, MLG, Auto-Tool |
| **Misc** | Auxiliary utilities | AI Assistant Integration, Command Terminal, Discord Rich Presence |

---

## Directory Configuration

Upon first execution, the client automatically creates the following directory structure for settings and assets:

```
Documents/
└── Hercule/
    └── Client/
        ├── Assets/
        │   └── Textures/    # Custom block & item icons (.png)
        ├── Scripts/         # Custom user-loaded .lua scripts
        └── default.hercule  # Active settings and layout configurations
```

---

## Lua Scripting API

Hercule includes a sandboxed Lua 5.4 interpreter. Users can create custom modules by placing `.lua` scripts in the Scripts directory.

<details>
<summary><b>Click to expand a basic Lua script example</b></summary>

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

## Legal & Disclaimer

> ⚠️ **Warning**

This software is intended strictly for educational, offline, and private single-player testing purposes. The developers do not condone or encourage cheating on public multiplayer networks.

- **Terms of Use:** Provided "as-is" without warranties. Reverse engineering, cracking, or unauthorized redistribution of the compiled binary is strictly prohibited.  
- **Account Safety:** Users assume full responsibility for any actions taken using this software. The development team is not liable for bans, suspensions, or restrictions on third-party networks.
```
