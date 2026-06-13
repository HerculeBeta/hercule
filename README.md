# Hercule Client

Hercule is a high-performance utility and automation client designed for Minecraft on Windows (Bedrock Edition). Built natively in C++, Hercule focuses on modularity, rendering efficiency, and security, featuring a customized Direct2D/DirectX rendering engine, a secure Lua scripting environment, and advanced pathfinding integrations.

---

## Key Architecture & Features

- **Dual-Renderer Interop:** Dynamically binds to both DirectX 11 and DirectX 12 swapchains using low-overhead hook methods, enabling seamless rendering of overlays, custom UI styles, and ESP overlays.
- **Embedded Lua 5.4 Engine:** Safely execute isolated scripts using a secure VM sandbox. Core C++ namespaces (`player`, `world`, `packet`, `render`) are bound to Lua to allow users to write custom modules without recompiling.
- **Advanced Pathfinding & Automation:** Integrated pathfinding algorithms (A*, JPS, and D* Lite) for ground navigation, block breaking, and automated obstacle avoidance.
- **Secure Authentication & Heartbeats:** Integrates with secure Cloudflare Worker gateways to verify client integrity, manage bans, and handle remote actions safely.

