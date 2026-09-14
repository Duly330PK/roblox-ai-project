# Roblox Project Instructions

## Project workflow

Roblox Studio is the runtime and DataModel authority.

Source code is synchronized through Roblox Studio Script Sync.

Use the Roblox_Studio MCP server to:
- inspect the live DataModel
- create and modify Roblox instances
- inspect scripts
- run Luau when appropriate
- start and control playtests
- inspect runtime output
- verify implemented changes

Do not infer the current Studio state from game.rbxlx when live Studio inspection is available.

## Synchronization

Script Sync roots:
- ServerScriptService
- ReplicatedStorage
- StarterPlayer.StarterPlayerScripts

Do not introduce Rojo or another synchronization system unless explicitly requested.

Do not create parallel copies of systems that already exist.

## Code placement

Keep server code in ServerScriptService.
Keep shared modules in ReplicatedStorage.
Keep client code in StarterPlayerScripts or another appropriate client container.

Prefer a small number of clear entry points and ModuleScripts over unnecessary framework layers.

## Development principles

Prefer simple, testable implementations.
Do not introduce frameworks, package managers, or large architectural abstractions unless they solve a demonstrated need.

Before making substantial changes:
1. inspect the relevant live Studio state,
2. understand the existing implementation,
3. make the smallest coherent change.

After implementing gameplay behavior:
1. run an appropriate playtest,
2. exercise the changed behavior,
3. inspect Studio output for warnings and errors,
4. fix discovered problems,
5. retest.

Do not claim a feature works without verifying it when verification is possible through Roblox_Studio MCP.

## Git

Do not discard unrelated user changes.
Keep commits focused and understandable.
