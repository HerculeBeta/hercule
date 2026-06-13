
Here is a professional, secure, and production-ready README.md for your Hercule Client GitHub repository. It focuses entirely on user-facing features, scripting, and general utility details while keeping your proprietary authorization, security, and backend systems completely confidential.
Hercule Client
Hercule is a high-performance, closed-source utility and modification client designed for Minecraft on Windows. Built with native C++, Hercule focuses on delivering modular extensions, stability, and a highly customizable interface with a minimal performance footprint.
For full guides and advanced documentation, visit the Hercule Wiki.
Key Capabilities
Modular Architecture: Includes over 120 built-in modules spanning combat, movement, world, and player utility categories.
Performance-Oriented Design: Rendered directly using DirectX interop to minimize frame-rate impact during active gameplay.
Highly Customizable HUD: An integrated HUD editor allowing drag-and-drop alignment of visual widgets, coordinates, direction trackers, and statistical panels.
Extensible Lua API: Features a built-in Lua 5.4 scripting VM, allowing advanced users to write, load, and test custom modules dynamically without needing to recompile the core client.
Feature Ecosystem
Hercule is organized into distinct categories based on utility:
Category	Primary Focus	Included Systems
Combat	Target acquisition & efficiency	Customizable Killaura, Reach tuning, and hit-registry utilities.
Movement	Pathfinding & travel	Fly, Speed, Step, and integrated ground pathfinders.
World	Environmental interaction	Scaffold, Nuker, and automated material-mining configurations.
Player	Inventory & state management	Auto-Armor, hotbar organization, and item blacklist dumping.
Visual	Spatial awareness & rendering	Detailed ESP (Block/Storage/Entity), Nametags, Minimap, and full World Map tracking.
Misc	Automation & helpers	In-game command console, translation engine, and macro binds.
Directory & Configuration Structure
Upon initialization, the client creates a dedicated local directory inside your Documents folder to safely read and write configurations:
code
Text
Documents/Hercule/Client/
├── Assets/
│   └── Textures/         # Custom block and item icons (.png)
├── Scripts/              # Custom .lua add-ons
└── Default.hercule       # Your active profile and module settings
Custom configurations can be managed in-game using the .config command or via the Settings panel in the ClickGUI.
Extensibility (Lua 5.4 Scripting)
The integrated Lua environment exposes a safe, restricted API to interface with the client and game environment. Below is a basic skeleton of a custom module:
code
Lua
local CustomFly = {}

-- Initialize the module within the client
module.register("CustomFly", "Basic movement example", "Movement", CustomFly)
module.addSlider("CustomFly", "Speed", "Velocity multiplier", 0.5, 5.0, 1.5)

-- Called when the module is turned off
function CustomFly.on_disable(self)
    player.setMotion(0, 0, 0)
end

-- Called every game tick (20 TPS)
function CustomFly.on_tick(self)
    local speed = module.get("CustomFly", "Speed")
    local moveForward = client.isKeyDown("w")
    
    if moveForward then
        local yaw, pitch = player.getRot()
        local rad = math.rad(yaw + 90)
        player.setMotion(math.cos(rad) * speed, 0, math.sin(rad) * speed)
    end
end
Licensing & Terms
Hercule is a proprietary, closed-source project.
Distribution: This software is distributed exclusively as a compiled binary. Reverse engineering, modifications of the binary, or unauthorized redistribution of the compiled DLL are strictly prohibited.
Disclaimer: Hercule is intended solely for educational, single-player, and authorized network testing. The developers are not responsible for any bans or blocks incurred on public servers. Use of modifications is at your own discretion.
