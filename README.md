# Carpet Fake Players

[![Minecraft](https://img.shields.io/badge/Minecraft-26.1.x%20%7C%2026.2%20%7C%2026.3-2ea44f)](https://modrinth.com/plugin/carpetfakeplayer)
[![Platforms](https://img.shields.io/badge/platform-Paper%20%7C%20Purpur-blue)](https://modrinth.com/plugin/carpetfakeplayer)
[![Java](https://img.shields.io/badge/Java-25-orange)](https://adoptium.net/)

**Carpet Fake Players** is a server-side fake-player plugin for **Paper and Purpur**. It lets server owners spawn and control fake players with player ownership, configurable limits, combat and item-use actions, persistent inventories, custom skins, sneaking, collision, gravity, knockback and rejoining.

- **Modrinth:** https://modrinth.com/plugin/carpetfakeplayer
- **Source:** https://github.com/ZynAyush/minecraft-playerbots

> This repository currently contains separate source projects for Minecraft 26.1.x, 26.2 and 26.3. Download or build the project that matches your server version.

## Compatibility

| Minecraft version | Supported server software | Java |
|---|---|---|
| 26.1.x | Paper / Purpur | 25 |
| 26.2 | Paper / Purpur | 25 |
| 26.3 | Paper / Purpur | 25 |

**Do not use a build made for a different Minecraft version.** These builds use version-specific server internals. Spigot, Bukkit standalone, Folia and other platforms are not listed as supported.

## Features

- **Server-side fake players:** Spawn and manage fake players directly on your server.
- **Player ownership:** Players control their own bots, with configurable per-player limits.
- **Persistent data and inventory:** Preserve bot inventories and data according to the configuration, including across supported removal, death and rejoin flows.
- **Combat actions:** Run a single attack, continuous attacks or attacks at a tick interval.
- **Item use:** Trigger a single use action, continuous use or interval-based use.
- **Inventory controls:** Select hotbar slots, manage offhand items, and drop an item, stack or inventory.
- **Custom skins:** Apply a skin using a player name.
- **Player-like movement:** Gravity, collision, natural knockback and explosion knockback.
- **Sneaking:** Toggle sneaking for individual bots.
- **Rejoining:** Recreate saved bots after they leave or are removed, restoring saved data according to configuration.
- **Original bots:** Create administrator-managed bots and grant or revoke access to original-bot management.
- **Integrations:** AuthMe compatibility and LuckPerms support.
- **Configuration:** Configure bot limits, attributes, hunger/exhaustion, persistence, physics, messages and other behavior in `config.yml`.

## Installation

1. Open the [Modrinth project page](https://modrinth.com/plugin/carpetfakeplayer).
2. Download the file matching your exact Minecraft version.
3. Stop your Paper or Purpur server.
4. Place the downloaded JAR in the server's `plugins/` directory.
5. Start the server.
6. Review the generated `plugins/PlayerBots/config.yml` and adjust it for your server.

Use only the build matching the server's Minecraft version.

## Commands

The main command is `/bot`.

### Bot management

```text
/bot spawn [name]
/bot kill [name|all]
/bot rejoin [name]
/bot info <name>
/bot hotbar <name> <0-8>
/bot offhand <name> <0-35>
/bot offhand <name> clear
/bot drop <name>
/bot dropstack <name>
/bot dropinv <name>
/bot sneak <name> on|off
/bot skin <name> <player>
/bot reload
```

### Combat

```text
/bot attack <name>
/bot attack <name> single
/bot attack <name> continuously
/bot attack <name> interval <ticks>
/bot attack <name> stop
```

### Item usage

```text
/bot use <name>
/bot use <name> single
/bot use <name> continuously
/bot use <name> interval <ticks>
/bot use <name> stop
```

### Original bots

```text
/bot original spawn <name>
/bot original grant <player>
/bot original revoke <player>
```

For the complete command syntax and version-specific notes, see the README inside the relevant source folder.

## Permissions

The plugin declares these permission nodes:

| Permission | Purpose |
|---|---|
| `bot.*` | Grants all PlayerBots permissions |
| `bot.admin` | Administrative controls |
| `bot.player` | Normal controls for owned bots |
| `bot.action` | Attack and item-use controls |
| `bot.use` | Normal bot-control commands for owned bots |
| `bot.rejoin` | Rejoin saved bots |
| `bot.kill-other` | Remove another player's bot |
| `bot.original` | Create/manage original bots |
| `bot.original.grant` | Grant or revoke original-bot access |
| `bot.reload` | Reload plugin configuration |
| `bot.mine` | Use the administrator-only mining action |

The exact defaults and permission inheritance are defined in each version's `plugin.yml`. Bot ownership checks remain enforced by the plugin: ordinary command permissions do not automatically allow a player to control another player's bot.

## Configuration

Configuration is generated at:

```text
plugins/PlayerBots/config.yml
```

The shipped configuration includes settings for:

- Global and per-player bot limits
- Default spawn name, game mode and entity attributes
- Gravity, collision, knockback and item pickup
- Inventory and experience behavior on death
- Attack and item-use reach and hunger exhaustion
- Autosaving and persistent rejoin snapshots
- Owner-offline timeout and warnings
- Join, leave and advancement messages
- AuthMe compatibility
- LuckPerms prefix handling
- Plugin messages and debug logging

Some settings require a server restart. Check the comments in the generated configuration for the exact behavior of each option.

## Building from source

Each supported Minecraft version has its own Gradle project.

| Version | Source directory |
|---|---|
| 26.1.x | [PlayerBots-26.1-full-source](PlayerBots-26.1-full-source/) |
| 26.2 | [PlayerBots-26.2-full-source](PlayerBots-26.2-full-source/) |
| 26.3 | [PlayerBots-26.3-full-source](PlayerBots-26.3-full-source/) |

Requirements: **JDK 25** and an internet connection for the initial Gradle/Paperweight dependency setup.

From the relevant version directory, run:

**Windows**
```bat
gradlew.bat clean build
```

**Linux / macOS**
```bash
./gradlew clean build
```

The compiled JAR is written to that project's `build/libs/` directory. Build each Minecraft version separately.

## Troubleshooting and bug reports

When reporting an issue, include:

- Minecraft version
- Paper or Purpur version
- Java version
- Plugin build/version
- Other plugins relevant to the issue
- Full console error or stack trace
- Steps to reproduce the problem

Please report issues through the repository's [GitHub Issues](https://github.com/ZynAyush/minecraft-playerbots/issues).

## License

See [LICENSE](LICENSE) for the license included with this source repository.

## Links

- [Download Carpet Fake Players on Modrinth](https://modrinth.com/plugin/carpetfakeplayer)
- [GitHub source repository](https://github.com/ZynAyush/minecraft-playerbots)
- [Report a bug](https://github.com/ZynAyush/minecraft-playerbots/issues)
