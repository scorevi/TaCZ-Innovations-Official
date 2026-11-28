# Mob Ammo Drops for Pack Creators

File: `tacz_mob_ammo_drops.js`

## What it does

Adds ammo drops on hostile mob death for calibers carried by the player. It is independent of fusion and does not require the kitbash runtime.

## Main configuration

| Key | Default | Meaning |
|---|---:|---|
| `dropChance` | `0.25` | Base drop chance |
| `minDropRatio` | `0.25` | Minimum fraction of magazine size |
| `minStackRatio` / `maxStackRatio` | `0.15` / `1.0` | Lower/upper fraction of the drop cap |
| `maxDropMags` | `6.0` | Caps a single drop to N reloads |
| `minSingleShotMaxDrop` | `6` | Upper cap floor for one-round guns |
| `hostileOnly` | `true` | Only monsters drop ammo |
| `scanBackpacksAndCurios` | `true` | Counts stored guns and reserves |
| `heldGunWeightMultiplier` | `4.0` | Favors the held gun |
| `heldStockedWeightMultiplier` | `1.5` | Reduced held bonus when stocked |
| `selfSustainingWeight` | `0.0` | Excludes self-sustaining (infinite-reload) calibers by default |
| `infiniteReloadAsSelfSustaining` | `true` | Treats infinite reload as self-sustaining |
| `lowReserveMags` / `lowReserveWeightMultiplier` | `2.0` / `3.0` | Boosts low-reserve calibers |
| `stockedReserveMags` / `stockedReserveStacks` / `stockedWeightMultiplier` | `12.0` / `1.5` / `0.2` | Deprioritizes stocked calibers |

## Behavior

- Matches drops to the calibers of the guns the player carries.
- Scans the player inventory, backpacks, shulkers, and Curios when enabled.
- Excludes guns with no real ammo type.
- Respects native extended-mag capacity.
- Treats infinite-reload guns as self-sustaining.

## Balance guidance

- `dropChance 0.25` is generous for combat packs; lower it for scarcity.
- Raise `maxDropMags` only if you want long boss fights to be self-sustaining.
- Keep `selfSustainingWeight` at `0` to avoid flooding players who already have self-sustaining guns.
- Backpack/Curios scanning makes drops feel smart but increases scanning cost.
- Fused guns are treated as normal guns; their ammo type comes from the chassis.

## Integration notes

- Optional: Curios, Sophisticated Backpacks.
- No config dependency on wildcard loot or kitbash.
- If drops are too frequent, check whether other mods also add ammo recovery or ammo-save effects.
