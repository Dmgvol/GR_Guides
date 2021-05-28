# GR Mod Loader

Mod Loader Download: [UnrealModLoader](https://github.com/RussellJerome/UnrealModLoader/releases) by RussellJerome.

Since this is new and the first question people ask: "What's a mod loader?" </br>
I would like to answer it before we begin:</br>
Traditionally we had to pack uassets so it will override original game files, but using the mod loader, allows us to use custom blueprints that are injected at runtime, giving us much more control without overriding game files.

**Note:** UE4 experience is required, the more the better. (if you want to create serious, advanced, cool mods)

Guide Table of Content:</br>
- GR Mod Loader
  - [UE4 Project Setup](#ue4-project-setup)
  - [Simple Mod Example (UIWidget)](#simple-mod-example-uiwidget)
  - [Packing the Mod](#build-and-pack-it)
  - [Using the ModLoader](#using-the-modloader)
  - [Simple Mod Examples](#simple-mod-examples)

</br>

## Mod Loader
Running it the first time will create an additional folder in Pak folder named `LogicMods`.</br>
This is where you place the packed mods into. 

## UE4 Project Setup
- Create a folder hierarchy `Mods/<ModName>`
- Create a Blueprint-Actor and named it `ModActor`.

![](Images/mod1.png)

- Open the Blueprint's EventGraph.
- Create two custom functions. (right click and look for "add custom event")
- Name them `PostBeginPlay` and `PreBeginPlay`.

![](Images/mod2.png)

## Simple Mod Example (UIWidget)

For this example I will display a simple UI Widget, to do so:
- Create a WidgetBlueprint (Right click, User interface > Widget Blueprint).
- Name it as you wish, I named it `SimpleWidget`.

![](Images/mod3.png)

Open it, place a simple text, change text, save, and close it

![](Images/mod4.png)

Go back to ModActor, add `Create Widget` node and pick the widget we've created.

![](Images/mod5.png)

Add `Add to Viewport` node and connect as shown

![](Images/mod6.png)

## Build and Pack it!
Packing is similar yet different, mod folder:</br>
`FirstMod/Ghostrunner/Content/Mods/FirstMod` </br>
(I called the mod `FirstMod`, and yes without `_P`)

Place the PAK file inside the `LogicMods` folder inside the usual `Paks` folder.

## Using the ModLoader
Note: **Close any running Unreal Editors or any other UE4 apps**

- Run `UnrealEngineModLauncher.exe` as Administrator.
- Should say "Waitng for Game Window..."
- Launch the game, you will see a lot of info showing up.
- Look for `Successfully Loaded <Modname>` - if everything is loaded properly.

---
## Simple Mod Examples

### Player TP
Will teleport the player 1000 units upwards when pressed F1

![](Images/mod8.png)

### Spawn Enemies (or any other BP)
Spawning Blueprints - Enemies (can spawn **any** BP)
Create an empty Blueprint-Character and name it `BP_EnemyShooterUzi` in `Content/ArtificialIntelligence/Characters/`

By doing this, we're creating a fake game reference, only the name and its folder is important, the game will do the rest.</br>
You can create much more fake blueprints/references by looking at the exported raw files or through UModel. (including models)

![](Images/mod9.png)

ModActor: EventGraph

![](Images/mod10.png)

### What's next?
Feel free to explore and create awesome mods.

If you're not experienced enough with UnrealEngine, I will suggest learning it so you will be able to create your own additional blueprints, behaviors, events, actors and link them all together.</br>
If you are an expert in unreal - well... I expect amazing mods from you!
