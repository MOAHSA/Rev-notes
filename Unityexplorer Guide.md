# Hacking IL2CPP Games with MelonLoader

## Introduction

Hacking IL2CPP games has never before been simpler than with
MelonLoader. MelonLoader allows you to run your own C# code inside an
IL2CPP game, making it almost trivial to enumerate objects, change their
properties, and call their methods. The integration of both MGUI and
HarmonyX allows for rapid GUI development and simple method hooking.

## What is IL2CPP?

IL2CPP (Intermediate Language to C++) is a Unity scripting backend that
aims to provide wider platform support for Unity games.\
It takes your C# code, converts it into Microsoft Intermediate Language
(MSIL), and then to C++.\
IL2CPP unintentionally makes hacking Unity games more difficult since
C++ code cannot be accurately decompiled and doesn't preserve symbol
information. Luckily, IL2CPP games ship with metadata that can be mapped
to game code, allowing you to examine a game's structure.

## Installing MelonLoader

1.  Download the latest version of the installer from the GitHub
    releases page.\
2.  Open the installer and browse to the directory containing your
    game's executable.\
3.  Leave all settings as default and press **Install**.\
4.  If successful, click **OK** and MelonLoader will be installed.

## Unity Explorer

Unity Explorer is an in-game GUI that lets you explore scenes and
objects, execute code, hook functions, and more.

### Installation

-   Download the correct release version of Unity Explorer for
    MelonLoader IL2CPP games.\
-   Run the game once, then extract all UnityExplorer files into the
    root game directory.\
-   Launch the game; the UnityExplorer UI should appear automatically
    (press **F7** if not).

### Features

-   **Object Explorer**: View the game's structure in a tree view.\
-   **Inspector**: View detailed information about object instances.\
-   **Console**: Execute custom C# code in-game.\
-   **Hooks Window**: Enumerate methods, create hooks, and toggle them
    on/off.

## Reverse Engineering IL2CPP Games

### Using dnSpy

-   Open dummy DLLs generated in `MelonLoader/Managed`.\
-   Inspect classes/methods, but expect missing code since IL2CPP strips
    most symbols.\
-   Developer naming conventions may help (e.g., `AddScore(int value)`).

### Using IL2CPP Dumper + IDA Pro

1.  Download and extract **IL2CPP Dumper**.\
2.  Select `gameassembly.dll` and metadata files.\
3.  Open `gameassembly.dll` in IDA Pro.\
4.  Load generated scripts (`script.json`, `il2cpp.h`) for symbol
    recovery.\
5.  Browse renamed functions for easier reversing.

## Developing a Melon (Mod)

### Setup

-   Create a new **C# Class Library** project in Visual Studio.\
-   Target **.NET Framework 6.0**.\
-   Add reference to `MelonLoader.dll`.\
-   Ensure `AssemblyInfo.cs` exists and configure mod metadata.

### Writing a Basic Mod

-   Inherit from `MelonMod`.\
-   Override lifecycle methods (e.g., `OnInitializeMelon`).\
-   Example: print "Hello World" to the in-game console.

### Building & Installing

-   Build project → output in `bin/Debug` or `bin/Release`.\
-   Copy `.dll` into the game root folder.\
-   Run game to load the mod.

## Advanced Example: Method Hooking

-   Add references to Harmony, game assembly, and Unhollower.\
-   Define a target class + method.\
-   Write a **Prefix Hook** to execute code before the method.\
-   Modify return values and control execution with `return false`.

## Conclusion

MelonLoader, combined with tools like Unity Explorer, IL2CPP Dumper, and
IDA Pro, provides a complete ecosystem for hacking Unity IL2CPP games.
By understanding IL2CPP and leveraging these tools, modders can inspect,
reverse engineer, and modify Unity games effectively.
