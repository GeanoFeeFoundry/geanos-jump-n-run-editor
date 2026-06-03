# Geano's Jump'n'Run Editor

Turn your FoundryVTT Scenes into playable Prince of Persia style platformer levels!

## 📋 Description

**Jump'n'Run** transforms the standard top-down Foundry VTT experience into a side-scrolling platformer. It introduces a physics engine, player controller, and level design tools allowing Game Masters to build challenging obstacle courses, puzzles, and action levels directly within Foundry.

Whether you want a simple jumping puzzle or a full-blown Metroidvania adventure, this module provides the tools to make it happen.

## ✨ Features

- **Side-Scrolling Physics**: Real-time gravity, jumping, wall-jumping, and collision detection.
- **Latest Updates (Patch Notes)**:
  - **Life System Styles**: Toggle between **Retro Hearts** (standalone UI) and **Character Sheet** (uses your system's HP) in the module settings.
  - **Hazard Customization**: Configurable damage variables for both **Fall Damage** and **Spike Hazards**.
  - **Dynamic Jump Scaling**: Added a toggle to switch between a fixed "General Max Jump Height" and "Character Sheet Max Jump Height."
  - **Attribute Mapping**: Define a specific data path (e.g., `system.abilities.ath.value`) and max value for character jump attributes; height now scales dynamically based on this value.
- **Level Editor Enhancements**:
  - **Platforms & Walls**: Define the physical geometry of your level.
  - **Hazards**: Spikes (with **Static** option to disable animation) and other dangers.
  - **Merging**: Select multiple overlapping elements of the same type and click "Merge" (via Bulk Config) to create complex, multi-shape structures that act as a single unit.
  - **Z-Ordering**: Use "Bring to Front" and "Send to Back" in the configuration dialogs to organize the layering of overlapping elements.
  - **Undo**: Press `Ctrl+Z` to undo up to 50 changes.
  - **Drag & Drop**: Move and resize elements easily. Hold `Shift` to snap to half-grid.
  - **Background Parallax**: Create depth with scrolling background layers (Scene Config).
- **Game Mechanics**:
  - **Hearts System**: Classic retro-style health tracking.
  - **Potions**: Placeable healing items.
  - **Checkpoints**: Set spawn points for players to restart from.
- **Integration**:
  - **Monk's Active Tile Triggers (MATT)**: Utilize custom triggers and actions for advanced logic.
  - **Codebase Refactor**: Cleanup of legacy remnants and resolved several minor stability issues.

## 🚀 Installation

1.  Copy the module's manifest URL: `https://github.com/GeanoFee/geanos-jump-n-run-editor/releases/latest/download/module.json`
2.  In FoundryVTT, go to **Add-on Modules** -> **Install Module**.
3.  Paste the URL and click **Install** or search for "Geano's Jump'n'Run Editor" via searchbar.

## 🎮 Usage

### 1. Activating a Scene
To turn a standard Scene into a Jump'n'Run level:
1.  Open the **Scene Configuration**.
2.  Go to the new **Jump'n'Run** tab (in Foundry v13 this became a section within the "Grid"-Tab).
3.  Check **Enable Jump'n'Run Mode**.
4.  (Optional) Configure **Gravity Force**, **Movement Speed**, and **Parallax** settings.

### 2. Building the Level
Use the **Jump'n'Run Tools** (Run icon) in the toolbar:
-   **Draw Platform**: Create solid ground.
-   **Draw Wall**: Create vertical barriers.
-   **Draw Hazard**: Create areas that deal damage.
-   **Draw Portal**: Teleport players between locations. Portals can be linked in the Element's config window.
-   **Draw Gates and Pressure Plates**: Gated open when a linked Pressure Plate is toggled. Gates and Plates can be linked in the Plates Element Config.
-   **Draw Checkpoint**: Set respawn points.
-   **Draw Start Point**: A Start Point behaves exactly like a Checkpoint, except Tokens that never touched a Checkpoint will automatically be revived at the Starting Point if it dies.
-   **Draw Ladders**: Create a space where Tokens can traverse vertically without being pulled down by gravity.
-   **Draw Crumpling Floor**: Create a Platform that will fall down after it has been touched.
-   **Draw Healing Potion**: Create a consumable that will automatically recover a missing Heart on touch. Healing Potions will automatically snap to the closest ground if possible.

#### Editor Controls
-   **Select**: Click to select. Shift+Click to add/remove from selection.
-   **Move**: Drag selected elements. Hold `Shift` to snap to half-grid.
-   **Resize**: Drag the bottom-right corner of an element. Hold `Shift` to snap to half-grid.
-   **Merge**: Select multiple elements of the same type, via Bulk Config -> "Merge Elements".
-   **Undo**: `Ctrl+Z` to revert changes.
-   **Context Actions**: Right-click an element to configure it (image, visibility, Z-order, etc).

*Tip: You can hide the hitboxes from players in the module settings for a more immersive look.*

### 3. Controls
Players control their assigned Token:
-   **Move Left/Right**: `A` / `D` or `Left Arrow` / `Right Arrow`
-   **Jump**: `Space` / `W`
-   **Drop**: `S` or `Down Arrow` (pass through some platforms)
-   **Wall Jump**: Press Jump while sliding down a wall.

## 🎯 Monk's Active Tile Triggers (MATT) Integration

This module adds custom Triggers and Actions to MATT, allowing for complex level scripting.

### Triggers
-   `Jump'n'Run: Player Death`
-   `Jump'n'Run: Health Change`
-   `Jump'n'Run: Portal Use`
-   `Jump'n'Run: Checkpoint Reached`
-   `Jump'n'Run: Item Collected`
-   `Jump'n'Run: Wall Jump`

### Actions
-   **Reset Hearts**: Restore a player's health to full.
-   **Modify Hearts**: Heal (positive) or Damage (negative) a player.
-   **Toggle Gravity**: Invert or disable gravity for the scene (0.0 to 1.0 toggle).

---
## License
This module is licensed under the [MIT License](LICENSE).

