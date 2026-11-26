# TaCZ Innovations

**Global loot table for guns and ammo, smart mob ammo drops, and anvil kitbashing for Timeless and Classics Zero (TaCZ).**

A modular set of KubeJS server scripts for Minecraft 1.21.1 / NeoForge. They add TaCZ guns and attachments to structure loot, keep players supplied with ammo, and turn the anvil into a kitbashing bench with fusion levels, catalysts, and level-scaled abilities.

Built for native TaCZ 1.21.1 (1.2.0+). No LootJS and no extra gun mods required.

> **Documentation scope:** Only the public configuration and gameplay are documented here.

## Install

1. Download the latest release and its `kubejs/` zip.
2. Copy the `kubejs/server_scripts/*` files into your instance's `kubejs/server_scripts/` folder.
3. Restart or run `/reload`, then check `latest.log` for `Kitbash fusion loaded` with no errors.

## Modules

| Script | What it does |
|---|---|
| `tacz_wildcard_loot.js` | Adds randomized TaCZ guns, attachments, spare ammo, and rare Jury-Rigged parts to structure containers. |
| `tacz_mob_ammo_drops.js` | Makes hostile mobs drop ammo for carried calibers, favoring held guns and low reserves. |
| `tacz_kitbash_fusion.js` | Anvil gun fusion, opt-in attachment welding/composites, fusion-level catalysts, and level-scaled abilities. |

## Highlights

- **Exploration rewards:** structure chests can contain usable, lightly kitted guns.
- **Loadout-aware ammo:** drops favor the gun in your hand and help when reserves are low.
- **Anvil kitbashing:** fuse guns (the stable core); welding and composites are opt-in via `CONFIG.fusionModes`.
- **Progression:** catalysts, donor-level inheritance, level-scaled stats, and one-shot ability identity rolls.
- **Pack-friendly:** rates, weights, chances, caps, catalysts, and ability gates are configurable.

## Gun Pack Compatibility

* **What is included:** The release archive contains only the KubeJS scripts. Third-party TaCZ gun packs are not bundled in the download.
* **Default support:** Works out of the box with the built-in **Timeless and Classics Zero** gun pack.
* **Additional gun packs:** The loot tables and anvil fusion system detect loaded TaCZ firearms automatically, so any extra gun packs you add to your instance (such as the 3-pack, 213-gun setup shown in the showcase videos) will work without extra setup.

## Showcase Videos

### TaCZ: Anvil Fusion - Proof of Concept
Early demonstration of combining weapons at the anvil and scaling base stats.

https://www.youtube.com/watch?v=NiuoTjjG1I0&pp=0gcJCUYIAYcqIYzv

### TaCZ: Bizarre Trifecta
Gameplay showcase testing fused weapon setups and attachment combinations in combat. Currently, only gun-gun fusion is enabled since attachment-attachment and gun-attachment fusions are work-in-progress and highly experimental, may contain bugs.

https://www.youtube.com/watch?v=SygBga3-XLI

More demonstrations and updates are posted on YouTube at [@scorevi](https://www.youtube.com/@scorevi). My uploads will be occasional, so don't expect some regular schedule :>

## Requirements

- Minecraft 1.21.1 / NeoForge 21.1.x
- KubeJS 2101.7.x
- Official TaCZ 1.21.1 (1.2.0+)
- At least one gun pack (Note: TaCZ already includes a default pack)
- Optional: GunsmithLib 7.1.3+ for fusion abilities (fusion and loot still work without it)

## Documentation

- [Documentation index](docs/README.md)
- [Player guides](docs/README.md#players)
- [Pack creator guides](docs/README.md#pack-creators)

## Compatibility

- Single-player / integrated-server scope; kitbash is guarded off on dedicated servers by default. No plans for multiplayer support.
- TaCZ APIs are version-sensitive, pin and test before updating a pack.
- The three scripts are independent; use any subset.
- No backports planned for 1.20.1 and older TaCZ versions, only current and upcoming future versions will be supported!

## License

Copyright (c) 2026 SP SCOREVI. All rights reserved. See [LICENSE.md](LICENSE.md).

## Credits

- [Timeless and Classics Zero (TaCZ)](https://github.com/MCModderAnchor/TACZ) - MCModderAnchor and the TaCZ team
- [KubeJS](https://github.com/KubeJS-Mods/KubeJS) - LatvianModder
- [GunsmithLib](https://github.com/ChloePrime/GunsmithLib) - ChloePrime
