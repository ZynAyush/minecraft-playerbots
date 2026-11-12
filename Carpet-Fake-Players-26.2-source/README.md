# Carpet Fake Players — Minecraft 26.2

This folder contains the source for the Minecraft 26.2 build. It targets Paper and Purpur 26.2.x and requires JDK 25.

See the [repository README](../README.md) for the plugin overview, common commands and permissions. Check the [Modrinth page](https://modrinth.com/plugin/carpetfakeplayer) for the latest downloadable release.

## Build

From this folder, run:

```bat
gradlew.bat clean build
```

On Linux or macOS, run:

```bash
./gradlew clean build
```

The JAR is written to `build/libs/` as `Carpet-Fake-Players-26.2-1.0.0.jar`.

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
/bot dropstack [name]
/bot dropinv [name]
/bot sneak [name] [on|off]
/bot skin [name] <player>
/bot reload
```

`single` is the default action mode. Repeating actions run on the server tick loop. If a normal player owns exactly one active bot, bot-control commands can target it without a name. With multiple owned bots, specify the name.

## Commands

The commands supported by this version are listed below.

## Compatibility

Use this build only with Minecraft/Paper 26.2.x. The version-specific server internals are under `src/main/java/dev/zynayush/carpetfakeplayers/nms/`. Paper and Purpur are supported. Folia and non-Paper server implementations are not listed as supported.
