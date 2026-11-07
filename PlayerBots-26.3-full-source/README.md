# Carpet Fake Players — Minecraft 26.3

Version-specific source project for Carpet Fake Players on Paper and Purpur 26.3.x.

For project features, installation notes and current releases, see the [Modrinth project](https://modrinth.com/plugin/carpetfakeplayer) and the [repository overview](../README.md).

## Build

Requires JDK 25 and an internet connection for the first Paperweight setup.

```bash
./gradlew.bat clean build
```

The resulting plugin JAR is written to `build/libs/` (artifact name: `PlayerBots-26.3-1.0.0.jar`).

## Commands

```text
/bot spawn [name]
/bot kill [name|all]
/bot kill_other <name>
/bot rejoin [name]
/bot info [name]
/bot attack [name] [single|continuously|interval <ticks>|stop]
/bot use [name] [single|continuously|interval <ticks>|stop]
/bot hotbar [name] <0-8>
/bot offhand [name] <0-35|clear>
/bot drop [name]
/bot dropstack [name] [item]
/bot dropinv [name]
/bot sneak [name] [on|off]
/bot skin [name] <player>
/bot mine [name] [single|continuously|interval <ticks>|stop]
/bot reload
```

`single` is the default action mode. Repeating actions run on the server tick loop. If a normal player owns exactly one active bot, bot-control commands can target it without a name. With multiple owned bots, specify the name.

## Permissions and ownership

The plugin declares `bot.*`, `bot.admin`, `bot.player`, `bot.action`, `bot.mine`, `bot.kill-other`, `bot.original`, `bot.original.grant`, `bot.reload`, `bot.rejoin`, and `bot.use`. Ownership is enforced separately from command permission checks: a bot is controlled by its owner, an operator, or an administrator with `bot.admin`. Administrative actions such as mining and managing another player's bot require the relevant administrative permission.

## Integrations and behavior

This version includes the implementation and configuration for server-side fake players, inventory persistence and rejoin snapshots, gravity/collision/knockback handling, player skins and sneaking, attack/use actions, and the optional LuckPerms and AuthMe integrations. Review `src/main/resources/config.yml` for configurable behavior.

## Compatibility

This source folder targets Minecraft/Paper 26.3.x. Use the build produced by this folder for the matching target; do not substitute a JAR built for another Minecraft target. Purpur is treated as a Paper-based compatibility target. Folia and non-Paper server implementations are not claimed as supported.

The version-specific NMS implementation is under `src/main/java/com/example/bot/nms/`.
