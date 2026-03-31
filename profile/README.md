# Parallax Framework

A modular roleplay framework for Garry's Mod, built for performance, structure, and developer clarity.

## What is Parallax?

Parallax is a roleplay framework that provides the core runtime for building roleplay gamemodes in Garry's Mod. It handles the systems that every roleplay server needs — characters, items, factions, inventories, commands, networking, hooks, and more — so that developers can focus on building the actual experience.

All framework functionality lives under the `ax` global namespace. Schemas (game-specific gamemodes) derive from Parallax via `DeriveGamemode("parallax")` and define the content: factions, items, classes, ranks, and gameplay logic specific to your setting.

Parallax also ships with a module system for optional features like admin tools, animations, a chatbox, containers, currencies, vendors, zones, and more. Modules can be shared across schemas without modification.

## What Parallax is Not

- **Not a standalone gamemode.** Parallax is the engine — you need a schema to play.
- **Not a fork.** Parallax is not derived from Nutscript, Helix, or Clockwork. It was built from scratch with a fundamentally different architecture.
- **Not plug-and-play.** This is a developer framework. It targets intermediate to advanced Lua developers who want control over their gamemode.

## How It Differs from Other Frameworks

### vs. Nutscript

Nutscript (~2014, by Chessnut & Black Tea) is a monolithic framework where the framework and schema are more tightly coupled. Plugins live inside the gamemode or schema's `plugins/` folder. It uses the standard GMod net library for networking, and character data is accessed via `character:setData()` with no explicit type system. The item system uses unique objects with persistence but no base-item inheritance hierarchy. Originally maintained by Chessnut, it's now community-maintained under the NutScript org with version 1.2 as the latest release (April 2024). Multiple forks exist, which has caused fragmentation.

### vs. Helix

Helix (~2018) is a direct successor to NutScript 1.1, retaining much of the same architecture with stability and feature improvements. It uses the standard GMod net library and a grid-based inventory system, same as Nutscript. Parallax and Clockwork both use weight-based inventories instead. Helix has a plugin ecosystem with a centralized Plugin Center. Its schema structure is similar to Parallax in that schemas derive from the framework, but there's no explicit module directory convention — plugins serve as the primary extensibility layer. The last formal release was in 2018 (beta), though development continued beyond that. The community remains active via Discord and continues to open pull requests on GitHub, but there have been no major updates ever since the beta release.

### vs. Clockwork

Clockwork (~2012, by kurozael/Cloud Sixteen) evolved from OpenAura (2010). It was originally commercial with licenses ranging from $30 to $200, later open-sourced under MIT in 2021. It uses a datastream/netstream abstraction rather than GMod's net library directly, which is considered dated by modern standards. Character data is intertwined with the player object via `player:SetCharacterData()` rather than using separate character objects. Clockwork has not been maintained since March 2021, and it cannot run on 64-bit servers — a hard limitation for modern deployments.

### What Parallax Does Differently

- **SFS binary networking.** A custom binary encoding layer with queue management replaces raw net messages and legacy datastream patterns.
- **Explicit type system.** `ax.type.string`, `ax.type.number`, `ax.type.bool`, `ax.type.data`, and others provide validation at the framework level and map directly to database column types.
- **Three-tier item hierarchy.** Base items, regular items, and instances are connected through metatabled inheritance, allowing shared behavior without duplication.
- **Hook interceptor layers.** Hooks flow through Schema, then Module, then Gamemode — giving schemas and modules first-pass control over framework behavior.
- **Hot-reload.** Time-filtered includes allow rapid iteration during development without restarting the server.
- **Active development.** 1,900+ commits and counting. Maintained by Riggs and bloodycop.

## Notable Repositories

| Repository | Description |
|---|---|
| [parallax](https://github.com/Parallax-Framework/parallax) | Core framework — runtime systems, modules, and documentation |
| [parallax-skeleton](https://github.com/Parallax-Framework/parallax-skeleton) | Minimal starter schema template for new projects |
| [parallax-hl2rp](https://github.com/Parallax-Framework/parallax-hl2rp) | Production Half-Life 2 roleplay schema |

## Quick Start

1. Clone the [parallax](https://github.com/Parallax-Framework/parallax) framework into your GMod `gamemodes/` directory.
2. Clone [parallax-skeleton](https://github.com/Parallax-Framework/parallax-skeleton) alongside it as your starting schema.
3. Configure your database connection and launch the server with your schema.

For detailed setup instructions, see the [documentation](https://parallax-framework.github.io/parallax/).

## Links

- [Documentation](https://parallax-framework.github.io/parallax/)
- [Discord](https://discord.gg/yekEvSszW3)
