# Wildcard Loot for Pack Creators

File: `tacz_wildcard_loot.js`

## What it does

Injects randomized TaCZ guns, attachments, spare ammo, and rare Jury-Rigged parts into structure container loot tables using KubeJS data generation. No LootJS dependency.

## Main configuration

| Key | Default | Meaning |
|---|---|---:|
| `chestDropChance` | `0.10` | Chance per container loot-table roll |
| `lootTablePathFilters` | chest/barrel/crate/shulker prefixes | Paths eligible for injection |
| `autoReloadForLateGunPacks` | `true` | Retry after TaCZ gun packs load after data generation |
| `maxAutoReloadAttempts` | `2` | Persistent reload-attempt cap across `/reload` |
| `startupPollIntervalTicks` | `20` | Wait between startup readiness checks |
| `startupReloadDelayTicks` | `20` | Delay before issuing `/reload` after a failed check |
| `minMagazines` / `maxMagazines` | `1` / `2` | Spare magazines per gun |
| `maxAmmoStacks` | `1` | Caps chest slots used by ammo |
| `allowOffSpecAttachments` | `true` | Allows rare off-whitelist parts |
| `lockOffSpecAttachments` | `true` | Keeps Jury-Rigged parts locked to their gun |
| `offSpecChancePerSlot` | `0.15` | Chance a rolled slot uses an off-spec part |
| `scaleGunWeightByTier` | `true` | Applies category weights |
| `defaultGunTypeWeight` | `5` | Fallback for unknown gun categories |

Supporting tables:

- `gunTypeWeights`: pistol `12`, SMG `9`, shotgun `8`, rifle `6`, DMR `4`, MG `3`, sniper `3`, RPG `1`
- `attachmentCountChances`: exact percentages from zero to six attachments
- `slotWeights`: relative slot pick weights
- `excludedLootTables`: fishing, bartering, archaeology, villager gifts, and other special tables

## Adding modded containers

Add the common loot-table path prefix to `lootTablePathFilters`, for example another `chests/` or `crates/` namespace. The script filters by path, not by hardcoded table IDs.

## Balance guidance

- Keep `chestDropChance` low for exploration packs; `0.05–0.15` is a sensible range.
- Raise attachment counts for military/loot-heavy packs, but a fully kitted gun should stay rare.
- Off-spec parts are thematic; lower `offSpecChancePerSlot` if they should be trophies.
- Off-spec parts only roll into usable slots, and native/integral attachments are never used as Jury-Rigged parts.
- Use `excludedLootTables` to keep special progression containers clean.
- The script is independent of fusion; it does not generate leveled fused guns or abilities.

## Troubleshooting

- Loot is generated when a container is first opened; previously opened containers do not change.
- Late-loading TaCZ packs can trigger a bounded startup reload. A healthy launch never reloads.
- Reload attempts persist across `/reload`; they reset when generation succeeds or when the startup check reports the loot is ready.
- Generated loot is cached and reused on later launches. The cache is regenerated automatically when the gun index, the wildcard config, or the container set changes. Delete the cache to force a full regeneration.
- Set `debug: true` in the script config for verbose `[tacz_wildcard]` diagnostics.
- Large packs can raise `startupPollIntervalTicks` / `startupReloadDelayTicks`, or set `autoReloadForLateGunPacks: false` and run `/reload` manually once TaCZ is ready.
- Use `/kjs reload server_scripts` for script-only changes.
- If no guns appear, confirm TaCZ gun data is loaded and check the path filters.
- Check `latest.log` for data-generation or index errors after adding packs.
