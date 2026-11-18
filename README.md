# Premade-GodotGUI
A Godot project template that also has a pre-made UI. Made it because I hate making menus over and
over again.

## Features:
- 3 menus (TitleScreen, Settings Menu and Credits Menu)
- awesome transition between scenes and levels using 
[Cashew Olddew's Transition Shader](https://github.com/cashew-olddew/Universal-Transition-Shader)

## Project Structure:

```text
res://
├── assets/                  # Shared media (fonts, global audio, tilesets, shaders)
├── data/                    # Concrete custom Resource instances (.tres)
└── src/
	├── autoload/            # Global singletons (Event bus, GameState, SceneManager)
	├── common/              # Reusable components, resource definitions, and utils (ex.In game Healthbar)
	├── entities/            # Dynamic actors (scene + script + local assets together)
	├── levels/              # Playable maps, rooms, and level logic
	└── ui/                  # Menus and in-game HUD overlays (ex. UI Health bar, Level counter)
```
## How to use it:
To avoid being redundant while working on m godot game, I like to put all the files I need in the same
folder for example, if I have a `Player` scene, I won't put the player sprites and all the code related 
to it in separate folders, this is annoying to manage because you have to dig through folders to find
what you need, instead when I make a `Player` scene I put everything related to it in `entities/`:

```text
├── entities/
	│   ├── enemies/
	│   │   └── goblin/
	│   │       ├── goblin.tscn
	│   │       ├── goblin.gd
	│   │       └── goblin_spritesheet.png
	│   └── player/
	│       ├── player.tscn
	│       ├── player.gd
	│       ├── player_spritesheet.png
	│       ├── player_jump.wav
	│       └── states/           # Player state machine
	│           ├── player_idle.gd
	│           ├── player_run.gd
	│           └── player_jump.gd
```
So if I need to change something, I know where to find in as little time as possible. A good rule of
tumb is to keep your project as modular as possible, so you don't have to make remake components over
and over again, modularity also helps with clean architecture and project readability.  

## Credits:
1. [Cashew Olddew's Transition Shader](https://github.com/cashew-olddew/Universal-Transition-Shader)
2. Kenny Menu assets
