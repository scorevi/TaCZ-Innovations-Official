# Kitbashing for Players

Kitbashing turns the anvil into a gun workshop. Put compatible items in the two input slots and take the result.

## What you can do

| Left | Right | Result |
|---|---|---|
| Gun | Gun | Transfers effective donor stats into the chassis. Strong donors can raise the output level. |
| Gun | Attachment | Welds the attachment into an open slot, including off-whitelist parts. |
| Attachment | Attachment | Combines same-type attachments into a layered composite. |

The left item is the base. The right item is the donor. Both are consumed.

Gun + gun is always available. The gun + attachment and attachment + attachment combinations are experimental and are only available when the pack enables them, so a pack may turn them off. Turning a combination off never changes items you already made with it — they keep working exactly as before.

Extended magazines are the exception: they cannot be combined into composites. A magazine's capacity comes from TaCZ's native level data, not from fusion.

## Fusion level and caps

- Guns start with a fusion limit of `3`; attachments start at `2`.
- The default hard gun limit is `20`; the attachment limit is `7`.
- Fusing at the current limit stops until you use a catalyst.
- Catalysts are applied with the fused item on the left and the catalyst on the right.

### Gun catalysts

| Catalyst | Cap gain | XP | Rule |
|---|---|---|---|
| Netherite Scrap | `+1` | `5` | Only while the gun cap is below `10`; cannot raise it past `10` |
| Netherite Ingot | `+2` | `8` | Up to hard cap `20` |
| Netherite Block | `+5` | `14` | Up to hard cap `20` |
| Beacon | `+6` | `16` | Up to hard cap `20` |

### Attachment catalysts

| Catalyst | Cap gain | XP | Rule |
|---|---|---|---|
| Netherite Scrap | `+1` | `5` | Up to cap `4` |
| Netherite Ingot | `+2` | `8` | Up to cap `7` |

Block and beacon are gun-only. If a catalyst would overshoot the cap, only the useful portion applies and the XP cost is prorated.

## What fusion improves

Fusion can transfer damage, armor pierce, headshot damage, pierce, spread, recoil, and chamber return. It can also weld donor attachments into open slots.

- Stats grow toward level-scaled ceilings, not instantly to the absolute maximum.
- Each fusion also adds a guaranteed portion of the remaining headroom.
- Existing stats above the current level ceiling are kept; they simply wait for the ceiling to rise.
- A heavily fused donor can raise the output's starting level, so high-end donors are worth using on a base gun.
- A donor with no transferable gain still advances the level and can roll abilities, showing `Level-up`.

## Abilities

Fused guns can develop colored `Ability:` lines, but an ability is an identity, not a guarantee. A fused gun may end up with none, one, or several:

- **Smart Lock**: curves bullets toward a target. `aim` favors the crosshair; `nearest` favors the closest hostile. Available from the first fusion.
- **Explosive Rounds**: adds an impact explosion. Unlocks around fusion level 5; you can also guarantee it by fusing a natively explosive donor.
- **Elemental Rounds**: adds on-hit effects such as fire, poison, weakness, slowness, or glowing. Unlocks around fusion level 9 and arrives with a set of effects.

Each ability is decided **once**, at the fusion that reaches its unlock level, and is fina. A gun that misses never gets it, and reloading cannot reroll it. Rarer abilities make each fused gun's identity matter.

Abilities grow stronger the further you fuse: a higher-level gun detonates harder (Explosive radius/damage scale with fusion level) and holds more Elemental effects (one at unlock, then one more every few levels).

Native explosive or igniting guns do not stack the emulated equivalent. A welded explosive magazine replaces emulated Explosive Rounds.

## Tooltip

Fused gear shows a compact `[KB]` block with chassis, donor, offense, chamber, spread, recoil, welded part, fusion level/cap, catalyst XP, and abilities. Older items restyle once when moved in an inventory.

## Practical tips

- Use a weak donor to level cheaply; use a strong donor when you want a real stat jump.
- Check the `Fusion: x/y` line before adding catalysts.
- Use scrap to reach cap `10`, then ingots/blocks/beacons for the final push.
- Keep a backup test world: fusion consumes both input items.
