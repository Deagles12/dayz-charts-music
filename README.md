# Charts Music (1983–2000) for DayZ

Charts Music is a cassette expansion for Zens Music. Version 2.0 defines 180 in-game cassette items spanning 1983–2000, with ten volumes per year.

## Features

- Each cassette has a unique class name, display name, playback duration and sound definition.
- The published mod groups the cassettes into three addons covering 1983–1988, 1989–1994 and 1995–2000.
- Server files provide Central Economy loot entries, a Dr_J0nes Trader configuration block and a class name list for admin tools.

## Dependencies and compatibility

Install [CF, Zens Core Mod and Zens Music alongside Charts Music](https://steamcommunity.com/sharedfiles/filedetails/?id=3742287199). Load them in that order, with Charts Music last. The cassette classes inherit from `Zen_Cassette_Base`, and the addon configs require `DZ_Data` and `ZenMusicBase`. Dr_J0nes Trader is optional and is needed only if you use its trader configuration block.

These files correspond to Charts Music 2.0. Playback uses Zens Music and requires the matching audio assets.

## Install the published mod

1. Subscribe to [Charts Music (1983–2000) on Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=3742287199) and install the dependencies on the client and server.
2. Enable the same mods on the client and server. For a dedicated server, include them in `-mod` in the order shown below. Use the actual folder names on your server.

   ```text
   -mod="@CF;@Zens Core Mod;@Zens Music;@Charts Music"
   ```

3. Copy `Keys/DeaglesChartsMusic.bikey` into the dedicated server's `keys` directory if you use the signed Workshop build.

## Use the cassettes

Use `ServerFiles/classnames.txt` to find a cassette's class name. For example, an admin can spawn `Zen_Cassette_DeaglesCharts1983Vol1` and play it using a compatible Zens Music device.

For loot spawns, merge the contents of `ServerFiles/types_deagles_charts_music.xml` into your mission's Central Economy types or register it as an additional types file. For Dr_J0nes Trader, insert the contents of `ServerFiles/TraderConfig_DeaglesChartsMusic_DrJ0nes_INSERT.txt` inside an existing `<Trader>` section.

## Build from source

The three directories under `addons/` contain the Workshop addon configs and PBO prefixes. This repository contains the mod configuration and server files. To build a playable copy, supply OGG audio you have permission to use in each addon's `data/sounds/` directory. Match the sample paths in `config.cpp` and adjust the configured playback durations if you use different recordings. Pack each addon separately with DayZ Tools, preserving its `$PBOPREFIX$`, and place the PBOs in your local mod's `Addons` directory. For a server that requires signatures, sign your build with your own key and install its corresponding public key on the server.

## License

The original configuration files in this repository are available under the MIT License. The license grant covers those files. Audio recordings and third-party mods are subject to their respective rights and terms.
