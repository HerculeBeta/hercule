<!-- HERO BANNER -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,100:2c5364&height=220&section=header&text=Hercule%20Client&fontSize=40&fontColor=ffffff&animation=fadeIn&fontAlignY=35" />
</p>

<p align="center">
  <b>High-performance modular Minecraft utility client for Windows</b><br/>
  Built for performance • Extensibility • Control
</p>

---

<!-- BADGES -->
<p align="center">
  <img src="https://img.shields.io/badge/Minecraft-v1.21.81.2-00c853?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows"/>
  <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Type-Proprietary-critical?style=for-the-badge"/>
</p>

---

## 🚀 Download

<p align="center">
  <a href="https://hercule.solisdev.xyz">
    <img src="https://img.shields.io/badge/⬇%20DOWNLOAD%20LAUNCHER-HERCULE%20CLIENT-00c853?style=for-the-badge&logo=windows&logoColor=white"/>
  </a>
</p>

<p align="center">
  <sub>Click above to get the latest launcher build</sub>
</p>

---

## ✨ Overview

<div align="center">

Hercule is a **modular C++ utility framework** designed for Minecraft on Windows.

</div>

It focuses on:
- ⚡ Low-latency rendering hooks
- 🧩 Modular architecture (120+ modules)
- 📜 Lua 5.4 scripting engine
- 🎛 Fully customizable HUD system
- 🧠 Developer-grade control tools

---

## ⚠️ Important Notice

> Hercule is a **closed-source proprietary project**.  
> This repository only contains documentation, scripts, and community resources.

---

## 🧩 Feature Modules

### ⚔️ Combat System
- Killaura
- TriggerBot
- Target Filtering
- AutoWeapon

### 🏃 Movement Engine
- Flight
- Velocity Control
- Step Assist
- Path Optimization

### 👁 Visual System
- BlockESP (3D)
- StorageESP
- Nametags
- Minimap Rotation

### 🌍 World Automation
- Scaffold
- Nuker
- Auto-Farming
- Schematic Printer

### 🎒 Player Tools
- Auto Armor
- Inventory Manager
- MLG Assist
- Auto Tool

### 🧰 Utilities
- Developer Console (F4)
- Lua VM Scripting
- Discord Rich Presence
- AI Assistant Bridge

---

## 🗂 Directory Structure

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

## 📜 Lua Scripting Engine

<p align="center">
  <img src="https://img.shields.io/badge/Lua-5.4-2C2D72?style=for-the-badge&logo=lua"/>
</p>

<details>
<summary><b>Expand Lua Example</b></summary>

```lua
local CustomFly = {}

module.register("CustomFly", "Advanced movement module", "Movement", CustomFly)
module.addSlider("CustomFly", "Speed", "Movement multiplier", 0.5, 5.0, 1.5)

function CustomFly.on_disable(self)
    player.setMotion(0, 0, 0)
end

function CustomFly.on_tick(self)
    local speed = module.get("CustomFly", "Speed")
    if client.isKeyDown("w") then
        local yaw = player.getRot()
        local rad = math.rad(yaw + 90)
        player.setMotion(math.cos(rad) * speed, 0, math.sin(rad) * speed)
    end
end
```

</details>

---

## 🎯 Performance Philosophy

<div align="center">

Low overhead • Direct rendering hooks • Native execution • Minimal latency impact

</div>

---

## ⚖️ Disclaimer

> This software is intended strictly for **educational and offline testing purposes only**.

- No liability for account actions
- No redistribution allowed
- Use at your own risk

---

<!-- FOOTER -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,100:0f2027&height=120&section=footer"/>
</p>

<p align="center">
  <sub>Hercule Client © 2026</sub>
</p>
