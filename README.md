# ECHOBOUND — Unity Prototype

ECHOBOUND is an original third-person action-adventure prototype built around one core mechanic:

> **Record your actions → create an Echo → let your past self repeat them.**

The prototype focuses on the foundation of the game described in the design specification: modular Unity C# systems, Echo recording/playback, basic player interaction, and a small test-room workflow.

## Current prototype

Implemented:
- Modular `PlayerController`
- `EchoSystem`
- Event/transform-based Echo recording
- Echo playback
- Basic interactable interfaces
- Lever and pressure-plate examples
- Basic enemy abstraction
- Health component
- Simple quest/progression data structures
- Save-system foundation
- UI hooks for Echo recording state
- Assembly-friendly folder structure

Planned:
- Full third-person combat
- Advanced enemy AI
- Multiple simultaneous Echoes
- Bosses
- Full world/regions
- Story/dialogue
- Skill tree and progression
- Final art, audio, VFX and cinematics

The source design specifically calls for starting with a single-room prototype before attempting the open world. It also recommends keeping the Echo system modular and recording structured actions rather than blindly recording every frame.

## Unity version

Recommended: **Unity 6 LTS or a compatible current Unity 6 release**.

This repository intentionally contains the source-code foundation rather than generated Unity `Library/`, `Temp/`, and build-cache folders.

## Project setup

1. Create a new **3D** Unity project.
2. Copy the `Assets/EchoBound` folder into the project's `Assets` directory.
3. Open the sample scene you create or build your own test room.
4. Add the required components described below.
5. Press Play and test the Echo recording/playback system.

## Suggested test room

Create:

- Player
- Door
- Lever
- Pressure plate
- One enemy

Test flow:

1. Enter the room.
2. Start Echo recording.
3. Move to the lever and interact.
4. Walk onto the pressure plate.
5. Stop recording.
6. Spawn/play the Echo.
7. Let the Echo repeat the sequence.
8. Use the opened route to reach the objective.

## Controls

The prototype intentionally keeps input integration simple. Connect your preferred Unity Input System actions to:

- Move
- Look
- Interact
- Start/stop Echo recording
- Play Echo

## Architecture

```text
Assets/
└── EchoBound/
    ├── Runtime/
    │   ├── Core/
    │   ├── Player/
    │   ├── Echo/
    │   ├── Interaction/
    │   ├── Combat/
    │   ├── AI/
    │   ├── Progression/
    │   ├── Quests/
    │   ├── Save/
    │   └── UI/
    ├── Editor/
    └── Samples/
```

Important systems:

```text
PlayerController
CombatSystem
EchoSystem
RecordingSystem
PlaybackSystem
EnemyAI
QuestSystem
ProgressionSystem
SaveSystem
UIManager
AudioManager
```

## Echo recording model

The design specification recommends structured recording:

```text
Timestamp
Position
Rotation
Action
Target
Ability
```

This prototype follows that principle through `EchoFrame` and `EchoAction` rather than relying only on raw per-frame transform recording.

## GitHub

Do not commit Unity-generated folders such as:

- `Library/`
- `Temp/`
- `Obj/`
- `Build/`
- `Logs/`
- `UserSettings/`

Use the included `.gitignore`.

## License

This repository contains original prototype code created for ECHOBOUND. Add a project-specific license before public distribution if desired.
