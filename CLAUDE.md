# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Unity 2022.3.35f1 project using the Universal Render Pipeline (URP). The package name is `com.spacetime.pvs.sample`.

## Unity Version & Key Packages

- **Unity**: 2022.3.35f1c1 (LTS)
- **Render Pipeline**: Universal Render Pipeline (URP) 14.0.11
- **Test Framework**: com.unity.test-framework 1.1.33
- **TextMeshPro**: 3.0.6
- **Timeline**: 1.7.6
- **Visual Scripting**: 1.9.4

## Development Workflow

Unity projects are edited primarily through the Unity Editor GUI, not the command line. Claude Code is most useful here for:

- Editing C# scripts in [Assets/](Assets/)
- Modifying project configuration files in [ProjectSettings/](ProjectSettings/)
- Managing package dependencies in [Packages/manifest.json](Packages/manifest.json)

## Running Tests

Tests use the Unity Test Framework. Run them via **Window > General > Test Runner** in the Unity Editor. There is no CLI test runner configured for this project.

## Git Submodules

This project contains three git submodules under `Packages/`:

| Submodule | Remote |
|-----------|--------|
| `Packages/com.spacetime.core` | git@github.com:xieliujian/com.spacetime.core.git |
| `Packages/com.spacetime.pvs` | git@github.com:xieliujian/com.spacetime.pvs.git |
| `Packages/com.spacetime.pvswrap` | git@github.com:xieliujian/com.spacetime.pvswrap.git |

**Rule: submodule code changes must only be made inside `D:\xieliujian\com.spacetime.core\Packages`**, committed and pushed as independent git operations in that directory. Never edit submodule files directly inside this sample project's `Packages/` folder.

## Project Structure

- [Assets/](Assets/) — All game assets, scenes, and scripts
  - [Assets/Scenes/](Assets/Scenes/) — Unity scene files (currently `SampleScene.unity`)
  - [Assets/Settings/](Assets/Settings/) — URP render pipeline asset configurations (Balanced, HighFidelity, Performant)
  - [Assets/TutorialInfo/](Assets/TutorialInfo/) — Editor-only readme/tutorial scripts
- [Packages/manifest.json](Packages/manifest.json) — Package dependencies
- [ProjectSettings/](ProjectSettings/) — Unity project settings (graphics, physics, quality, etc.)

## URP Configuration

Three quality tiers are configured under [Assets/Settings/](Assets/Settings/):
- `URP-Performant` — lowest quality, best performance
- `URP-Balanced` — default mid-tier
- `URP-HighFidelity` — highest quality

The active profile per scene is set in [Assets/Settings/SampleSceneProfile.asset](Assets/Settings/SampleSceneProfile.asset).
