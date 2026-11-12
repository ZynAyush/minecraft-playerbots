# Carpet Fake Players

Carpet Fake Players is a Paper and Purpur plugin for spawning and managing server-side fake players. Players can manage their own bots when given the right permissions; server operators keep the administrative controls.

**Downloads:** [Modrinth](https://modrinth.com/plugin/carpetfakeplayer)  
**Source:** https://github.com/ZynAyush/carpet-fake-players  
**Platforms:** Paper and Purpur  
**Java:** 25

## Supported versions

| Minecraft | Server | Java |
|---|---|---|
| 26.1.x | Paper / Purpur | 25 |
| 26.2 | Paper / Purpur | 25 |
| 26.3 | Paper / Purpur | 25 |

The builds use version-specific server internals. Install the JAR that matches the server's Minecraft version. Spigot, standalone Bukkit and Folia are not listed as supported.

## What it can do

- Spawn fake players and assign ownership.
- Set global and per-player bot limits.
- Save bot inventories and restore saved bots where the configured rejoin rules allow it.
- Control a bot's hotbar, offhand, equipment and sneaking state.
- Run single, continuous or interval-based attack and item-use actions.
- Apply skins by player name.
- Configure gravity, collision, knockback and item pickup.
- Manage administrator-owned original bots.
- Integrate with LuckPerms and AuthMe.

## Install

1. Open the [Modrinth page](https://modrinth.com/plugin/carpetfakeplayer).
2. Download the release for the exact Minecraft version on your server.
3. Stop the Paper or Purpur server.
4. Put the JAR in `plugins/` and start the server again.
5. Review `plugins/Carpet Fake Players/config.yml` before opening the feature to players.

Back up the server before changing plugins or configuration. Test major changes on a staging server when possible.

## Commands

The command root is `/bot`.

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

### Item use

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

The version folders contain their own command notes. Check the matching README if a command differs between game versions.

## Permissions

| Permission | Purpose |
|---|---|
| `bot.*` | All plugin permissions |
| `bot.admin` | Administrative controls |
| `bot.player` | Controls for bots the player owns |
| `bot.action` | Attack and item-use actions |
| `bot.use` | Standard controls for owned bots |
| `bot.rejoin` | Rejoin saved bots |
| `bot.kill-other` | Remove another player's bot |
| `bot.original` | Manage original bots |
| `bot.original.grant` | Grant or revoke original-bot access |
| `bot.reload` | Reload configuration |
| `bot.mine` | Administrator-only mining action |

Ownership checks are separate from command permissions. A player with a general command permission cannot automatically control someone else's bot.

## Build from source

Each Minecraft target has a separate Gradle project:

| Minecraft | Source folder |
|---|---|
| 26.1.x | `Carpet-Fake-Players-26.1-source/` |
| 26.2 | `Carpet-Fake-Players-26.2-source/` |
| 26.3 | `Carpet-Fake-Players-26.3-source/` |

Use JDK 25. From the folder for your target version, run `gradlew.bat clean build` on Windows or `./gradlew clean build` on Linux/macOS. The JAR is written to `build/libs/`.

## Bug reports

Open an issue in this repository and include the Minecraft version, Paper/Purpur build, Java version, plugin version, relevant configuration, related plugins and a full error log. Remove server addresses, tokens and other private information before posting.

## License

See [LICENSE](LICENSE) for the terms that apply to this source repository.
