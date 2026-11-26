# TaCZ Innovations

**An addon containing unconventional prototype mods for Timeless and Classics Zero (TaCZ).**

A modular, bundle of KubeJS server scripts for Minecraft 1.21.1 / NeoForge and TaCZ 1.2.0+, exclusively made for **single-player** only. 

It adds TaCZ guns and attachments to structure loot from all kinds of vanilla and modded structures existing in your pack with balance, keep your arsenal supplied with ammo on the go, and turns the anvil into a kitbashing / welding bench with fusion levels, catalysts, and level-scaled abilities. Yeah who actually makes the regular anvil do something beyond it's intended job?! You serious?!

### Why I've built this 
The sole reason why I made these mods is because I've been long wanted to explore untapped, a bit unconventional capabilities of TaCZ that can be adapted anywhere with various gunpacks, where in it actually improves the gun and attachment stats natively without going onto extremes or traditional crafting recipes, **have its own identity** and avoiding that generic feeling, something the mainstream addons existing in the modding platforms are lacking. Although, you can have the progressive feeling back by levering a switch in the config.

## Screenshots (not limited to)

### Anvil Kitbashing
Regular anvil is primarily used for weapon fusions and welding. No custom or specialized workbench is required.

#### Gun + Gun Fusion
<img width="932" height="681" alt="image" src="https://github.com/user-attachments/assets/bfaf7732-3cba-44a2-8983-d9a1a2ad45f1" />
<img width="1882" height="974" alt="image" src="https://github.com/user-attachments/assets/9d417c3c-8b0c-451c-8bfa-13b71fb4640a" />

### Attachment + Attachment Fusion (WIP)
<img width="807" height="544" alt="image" src="https://github.com/user-attachments/assets/6ac030ef-fcf2-4cb8-95fb-e3d627532ba0" /> 

### Gun + Attachment Fusion (WIP)

**Warning: Gun may show weird attachment positional issues when welded with Jury-Rigged (off-spec) attachments. Once an attachment fusion is welded to a gun, it is permanently attached. It cannot be detached.**

**Jury-rigged welded gun:**

<img width="712" height="574" alt="image" src="https://github.com/user-attachments/assets/e4814366-bf2c-4161-9008-0feda3dd4c23" />

**Normal attachment welded gun:**
<img width="837" height="523" alt="image" src="https://github.com/user-attachments/assets/2ff76a72-c12b-44b1-ade1-e3a708edb414" />
<img width="1250" height="707" alt="image" src="https://github.com/user-attachments/assets/41a79efd-f5b2-4d37-8e4f-f518d968af2b" />

## Requirements

- Minecraft 1.21.1 / NeoForge 21.1.x
- KubeJS 2101.7.x
- Official TaCZ 1.21.1 (1.2.0+)
- At least one gun pack (Note: TaCZ already includes a default pack)
### Optional:
- GunsmithLib 7.1.3+ for **fusion abilities** 
  * Fusion and loot still work without it

## Compatibility

- Single-player and integrated-server scope; kitbash is guarded off on dedicated servers by default. No plans for multiplayer support, unless you pay me well enough to do so.
- TaCZ APIs are version-sensitive, pin and test before updating a pack.
- The three scripts are independent; use any subset.
- As indicated in the requirements. Only current and upcoming future TaCZ versions will be supported!

### Gun Pack Compatibility

* **Inclusions:** The release archive contains only the KubeJS scripts. Third-party TaCZ gun packs are not bundled in the download.
* **Default support:** Works out of the box with the built-in **Timeless and Classics Zero** gun pack.
* **Additional gun packs:** The loot tables and anvil fusion system detect loaded TaCZ firearms automatically, so any extra gun packs you add to your instance will work without extra setup.

## Install

1. Download the latest release '.zip' located at the right sidebar of this page.
2. Extract and copy the `kubejs/server_scripts/*` files into your instance's `kubejs/server_scripts/` folder.
3. Restart or run `/reload`, then check `latest.log` to make sure they loaded properly with no errors from KubeJS.

## Modules

| Script | Function |
|---|---|
| `tacz_wildcard_loot.js` | Adds randomized TaCZ guns, attachments, spare ammo, and rare Jury-Rigged parts to structure containers. |
| `tacz_mob_ammo_drops.js` | Makes hostile mobs drop ammo for carried calibers, favoring held guns and low reserves. |
| `tacz_kitbash_fusion.js` | Anvil gun fusion, opt-in attachment welding/composites, fusion-level catalysts, and level-scaled abilities. |

## Highlights

- **Exploration rewards:** structure chests including open ones can contain usable, customized guns with varying attachments. Not all the time you get so much guns out of the bat. Bonus chests are excluded.
- **Loadout-aware ammo:** drops favor the gun in your hand and help when reserves are low. Really depends on your weapon team compositions
- **Anvil kitbashing:** fuse guns with ease. Welding and composites are opt-in via `CONFIG.fusionModes`. If you want to experiment the unstable one, go ahead while it's in the works.
- **Progression:** catalysts, donor-level inheritance, level-scaled stats, and one-shot ability identity rolls. Yeah diversity let's go!
- **Pack-friendly:** rates, weights, chances, caps, catalysts, and ability gates are HIGHLY configurable. From time to time I may balance certain values out there without notice.

NOTICE: The configuration's baselines are adjusted with balance according to TaCZ's default gun pack and configuration. So barebones and no 3rd-party gun packs. Though I tested these on other small to large modpacks like ATM and TNP LL8.

## Showcase Videos

### TaCZ: Anvil Fusion - Proof of Concept
Early demonstration of combining weapons at the anvil and scaling base stats.

https://www.youtube.com/watch?v=NiuoTjjG1I0&pp=0gcJCUYIAYcqIYzv

### TaCZ: Bizarre Trifecta (no edits)
Gameplay showcase testing fused weapon setups and attachment combinations in combat. Currently, only gun-gun fusion is enabled since attachment-attachment and gun-attachment fusions are work-in-progress and highly experimental, may contain bugs.

https://www.youtube.com/watch?v=SygBga3-XLI

More demonstrations and updates are posted on YouTube at [@scorevi](https://www.youtube.com/@scorevi). My uploads will be occasional, so don't expect some regular schedule :>

## Documentation (must read!)

- [Documentation index](docs/README.md)
- [Player guides](docs/README.md#players)
- [Pack creator guides](docs/README.md#pack-creators)

## Support and FAQ

Use the GitHub issue tracker:

**https://github.com/scorevi/TaCZ-Innovations-Official/issues**

Include Minecraft, NeoForge, KubeJS, TaCZ, and GunsmithLib versions, your gun pack/addon list, the relevant `latest.log` section, and reproduction steps.

Q: Will you upload this addon to **CurseForge** or Modrinth?

A: At the right time, so give me a break :)

Q: Can you port this as a Java mod or do a backport?

A: Not planned. Time will tell.

Q: Do you have discord server?

A: None at the moment, probably will not have one I'm strictly on forums or YouTube. And I don't want to deal with so much personal messages.

Q: Can you add 'x' feature?

A: No, unless it is viable and innovative, and of course in-demand. And really depends on how busy I am in the real world.

Q: World bugged out or item isn't outputting, glitching or has weird UI bugs on the guns

A: **Refer to the documentation first before opening an issue unless your logs show KubeJS errors.** About the guns' attachment bugging out, that's normal and expected if you welded a non-native, unsupported attachment to the gun. Anything about gun packs' weapon balancing or attachment issue, I'm off-limits. I only provide the foundation.

Q: Will it conflict with 'x' mod?

A: No since it isn't a java mod, duh. If it conflicts with a pack's KubeJS script, be warned I may not provide support for that.

Q: When will you update this addon?

A: Whenever I'm free and in mood, and motivated enough to do so.

## License

Copyright (c) 2026-2027 SP SCOREVI. All rights reserved. See [LICENSE.md](LICENSE.md).

## Credits

- [Timeless and Classics Zero (TaCZ)](https://github.com/MCModderAnchor/TACZ) - MCModderAnchor and the TaCZ team
- [KubeJS](https://github.com/KubeJS-Mods/KubeJS) - LatvianModder
- [GunsmithLib](https://github.com/ChloePrime/GunsmithLib) - ChloePrime

## Authors
- @scorevi (lead developer, no one else)
- AI tools for the repetitive, boring detail stuff!

## AI Usage Disclosure

Ah yes, the most **important** out of all sections listed here since the rise of uncanny slop. I admit myself, I did use to some extent. Rather be real than sugarcoat it.
**The core concept, system design, scaling math, mod ecosystem research, in-game playtesting, and balance tuning for this addon were created manually by me.**

Every script, formula, and configuration value are manually reviewed, adjusted, and verified in-game before release. Lots of testing, lots of generic worlds out there when I want to chill out. No AI-generated images, icons, or video assets are used anywhere in this project, not even the showcases. I don't have enough funds like the bros out there to waste on such thing. Rather be doing that in Paint.NET, the old way.

AI tools were used in a light-to-moderate capacity for these:
* **Repetitive code and configuration structure:** Generating boilerplate patterns and laying out editable `CONFIG` blocks. Yeah you heard that right, I am messy with code but kinda perfectionist in some ways.
* **Release packaging scripts:** Automating comment stripping and zip packaging for public builds. Ugh, just like assembling a damn thing.
* **English documentation:** Editing grammar and phrasing in `README.md` and `docs/` as a non-native English speaker (I'm from SE Asia, so expect some inconsistent grammar).
