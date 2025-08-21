# UnityExplorer - In-Game UI for Unity Games

**UnityExplorer** is an in-game user interface designed for **exploring, debugging, and modifying IL2CPP and Mono Unity games**. It supports most Unity versions from 5.2 to 2021+ and is powered by UniverseLib.

---

## Key Features

* **Inspector API**
  Inspect objects or types from outside the C# console using the `InspectorManager` class.
  Example:

  ```csharp
  UnityExplorer.InspectorManager.Inspect(theObject); // Inspect an object
  UnityExplorer.InspectorManager.Inspect(typeof(SomeClass)); // Inspect a type
  ```

* **Object Explorer**

  * **Scene Explorer Tab**: Browse active scenes, including `DontDestroyOnLoad` and `HideAndDontSave` objects.

    * "HideAndDontSave" contains flagged objects plus assets/resources not in any scene.
    * Scene Loader allows loading scenes in the build (may not work for Unity 5.X).
  * **Object Search Tab**: Search for Unity objects, GameObjects, Components, C# Singletons, or Static Classes.

* **Inspector**
  View detailed object information, manipulate values, and inspect C# classes with reflection.

  * **GameObject Inspector `[G]`**: Inspect GameObjects, transforms, and components.
  * **Reflection Inspectors `[R]`/`[S]`**: Inspect other objects; supports Texture2D, Image, Sprite, Material (View/Save as PNG), AudioClip (Play/Save as WAV).

* **C# Console**
  Run REPL code or define temporary classes using `Mono.CSharp.Evaluator`.

  * Automatic startup script: `startup.cs` in `sinai-dev-UnityExplorer\Scripts\`.
  * Clipboard helpers: `Copy(obj)` and `Paste()`.

* **Hook Manager**
  Hook methods with a click for debugging. Edit generated hook source. Accepted hook types: `Prefix`, `Postfix`, `Finalizer`, `Transpiler`.

* **Mouse-Inspect**
  Inspect objects under the mouse:

  * **World**: Uses `Physics.Raycast`.
  * **UI**: Uses `GraphicRaycasters`.

* **Freecam**
  Free camera controlled via keyboard/mouse. Works even when UnityExplorer UI is hidden.

* **Clipboard**
  View/clear current paste value. Copy/paste values between reflection inspectors, enumerables, dictionaries, and other inspector targets.

---

## Installation

* **BepInEx**

  1. Unzip release into a folder.
  2. Copy `plugins/sinai-dev-UnityExplorer` to `BepInEx/plugins/`.

     * Note: BepInEx 6 available at [builds.bepinex.dev](https://builds.bepinex.dev).

* **MelonLoader**

  1. Unzip release.
  2. Copy DLL from `Mods` folder into MelonLoader `Mods`.
  3. Copy DLLs from `UserLibs` to MelonLoader `UserLibs`.
  4. Extract all files into the game root directory. Press **F7** if UI doesn't appear.

* **Standalone**
  Requires manual dependency loading (UniverseLib, HarmonyX, MonoMod).

  1. Load required libraries.
  2. Start Il2CppAssemblyUnhollower if needed.
  3. Load UnityExplorer DLL.
  4. Create instance:

  ```csharp
  UnityExplorer.ExplorerStandalone.CreateInstance();
  ```

  5. Optionally subscribe to logging events.

* **Unity Editor**

  1. Download `UnityExplorer.Editor`.
  2. Install via Package Manager or manually drag folder into `Assets`.
  3. Drag `Runtime/UnityExplorer` prefab into scene or create GameObject and add `Explorer Editor Behaviour`.

---

## Common Issues & Solutions

* **Config files:**

  * BepInEx: `BepInEx\config\com.sinai.unityexplorer.cfg`
  * MelonLoader: `UserData\MelonPreferences.cfg`
  * Standalone: `{DLL_location}\sinai-dev-UnityExplorer\config.cfg`

* **Recommended settings:**

  * `Startup_Delay_Time`: 5–10 seconds to prevent startup corruption.
  * `Disable_EventSystem_Override`: Set to `true` if input does not work.

For unresolved issues, create an issue on GitHub.

---

## Repository & Video Links

* **GitHub Repository**: [GrahamKracker/UnityExplorer](https://github.com/GrahamKracker/UnityExplorer)

  * Forked from: `sinai-dev/UnityExplorer`
  * License: GPL-3.0
  * Languages: C# (98.3%), PowerShell (1.7%)
  * Stars: 171 | Forks: 24

* **Related Video (Info)**:

  * Title: "How to Hack il2cpp Games - MelonLoader Tutorial"
  * Channel: "Guided Hacking"
  * Note: Direct YouTube link not provided in sources.

---

## Disclaimer

**UnityExplorer** is in no way associated with Unity Technologies. "Unity", Unity logos, and other Unity trademarks are trademarks or registered trademarks of Unity Technologies or its affiliates in the U.S. and elsewhere.
