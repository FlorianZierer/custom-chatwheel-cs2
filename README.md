![20250803220240_1](https://github.com/user-attachments/assets/2c74f559-e866-4a7c-8a02-2808953a0ba5)

# 📌 Custom Chat Wheel for CS2

This project provides a configuration for creating highly customized chat wheels in Counter-Strike 2. It allows users to execute complex commands and add **custom labels directly to the chat wheel for clarity**.

The initial concept was inspired by a video from [MrMaxim](https://www.youtube.com/watch?v=uVktG6VXFwA). The methods for implementing and refining the chat wheels were drawn from [CSAFAP-config-package](https://github.com/FNScence/CSAFAP-config-package), a comprehensive configuration collection that laid the groundwork for this project.

## ✨ Features

  * **Threefold Radial Menus:** Configure up to three separate chat wheels, each with eight customizable slots.
  * **Custom Text Labels:** Define your own text labels for each slot.
  * **Command Execution:** Assign any console command to a slot.
  * **Chain Multiple Commands:** Execute multiple commands from a single slot.
  * **Native Radio Lines:** Integrate standard Valve radio commands like `#Chatwheel_requestweapon` or `#Chatwheel_midplan`.
  * **100% Safe & Compatible:** Works flawlessly in Valve Matchmaking, Premier, and on FACEIT. This config relies purely on standard console commands and is `sv_cheats 0` compliant.

## ⚙️ Installation

1.  Click the green **`< > Code`** button on the main repository page and select **Download ZIP**.
2.  Unpack the downloaded ZIP file.
3.  Navigate to your CS2 game installation folder. The default location is typically:
    `C:\Program Files (x86)\Steam\steamapps\common\Counter-Strike Global Offensive\game\`
    > **Tip:** To find this folder, right-click CS2 in your Steam Library → `Manage` → `Browse local files`, then open the `game` folder.
4.  Drag the `csgo` folder from the downloaded files into your `.../game/` directory. When prompted to merge the folders, click **Yes**.

## 🔧 Configuration

Follow these steps to customize your chat wheels.

### Step 1: Define Your Text Labels

All custom text displayed on the chat wheel is defined in a localization file.

1.  Open the file: `csgo/resource/platform_english.txt`
2.  Change the text in the second column to what you want the chat wheel to display.

**Example:**

```csharp
// Labels for Chat Wheel 1
"Wheel_1_slot_1_label"        "Radar: D2"
"Wheel_1_slot_2_label"        "Radar: Mirage"
"Wheel_1_slot_7_label"        "Volume: Casual"
"Wheel_1_slot_8_label"        "Volume: Comp"
```

### Step 2: Assign Commands to Slots

Link your labels to in-game actions.

1.  Open the file: `csgo/cfg/chatwheels/setup_chatwheels.cfg`
2.  Assign one or more commands to each alias. Use a semicolon (`;`) to separate multiple commands.

**Example:**

```csharp
alias "wheel_1_slot_1" "cl_radar_scale 0.35"
alias "wheel_1_slot_2" "cl_radar_scale 0.4"
alias "wheel_1_slot_7" "volume 0.03"
alias "wheel_1_slot_8" "volume 0.55"
```

### Step 3: Set Your Keybinds

You must bind a key to open the chat wheels directly in your configuration file or the console. **Do not use the in-game settings menu for this.**

1.  Open `csgo/cfg/chatwheels/setup_chatwheels.cfg`.
2.  Add the following `bind` command, replacing `KEY` with your desired key.

<!-- end list -->

```csharp
// --- Keybind ---
bind "KEY" "+open_chatwheel"
```

### Step 4: Activate the Configuration

To ensure your chat wheel settings load every time you start the game, you must execute the setup file from your `autoexec.cfg`.

1.  Add the following line to your `autoexec.cfg`:
    ```csharp
    exec chatwheels/setup_chatwheels.cfg
    ```
2.  Save your `autoexec.cfg`. Your custom chat wheels will be active the next time you launch CS2.
