# Kitbashing for Pack Creators

## Requirements

- Minecraft 1.21.1 / NeoForge 21.1.x
- KubeJS 2101.7.x
- Native TaCZ 1.21.1, 1.2.0+
- Optional GunsmithLib 7.1.3 for Smart Lock, Explosive Rounds, and Elemental Rounds

No TaCZ JS dependency. The loot and mob-drop scripts are independent and optional.

## Fusion modes

Each anvil input combination is toggled independently under `CONFIG.fusionModes`:

| Key | Mode | Default |
|---|---|---|
| `gunGun` | A: gun + gun | `true` |
| `gunAttachment` | B: gun + attachment weld | `false` |
| `attachmentAttachment` | C: attachment + attachment composite | `false` |

- Only Mode A ships enabled. Modes B and C are experimental — enable them deliberately. B and C only unlock on an explicit `true`; `gunGun` stays on unless set to `false`.
- Mode D (cap catalysts) is gated separately by `CONFIG.catalyst.enabled`.
- Disabling a mode only affects new anvil operations; existing fused items keep their stored data and remain catalyst-upgradable.

## Baseline rules

- Gun fusion limit starts at `3`; hard cap `20`.
- Composite attachment limit starts at `2`; hard cap `7`.
- Extended magazines cannot be fused into composites; capacity follows TaCZ's native level data.
- Fusion XP cost scales with the fusion count and is clamped by `limits.maxXpCost`.

## Catalyst configuration

`CONFIG.catalyst.items` is gun-only; `CONFIG.catalyst.attachmentItems` is composite-only.

| Catalyst | Gun yield | Gun XP | Attachment yield | Attachment XP |
|---|---:|---:|---:|---:|
| Netherite Scrap | `+1`, max cap `10` | `5` | `+1`, max cap `4` | `5` |
| Netherite Ingot | `+2` | `8` | `+2`, max cap `7` | `8` |
| Netherite Block | `+5` | `14` | not allowed | - |
| Beacon | `+6` | `16` | not allowed | - |

- Full cap gains cost the listed XP; partial gains prorate XP.
- `requireAtCap` can force catalysts to be used only after reaching the current cap.
- Catalyst lore shows the actual XP cost.

## Stat progression

- `gunFusion.statCurveExponent` controls the level-scaled stat ceiling (default `0.72`).
- `statTargets` set the per-stat ceiling; retune per pack so no gun is left without headroom.
- `guaranteedStatShare` (default `0.25`) adds a floor per fusion.
- `levelScaledStatCap: false` restores absolute ceilings.
- Existing bonuses above the current ceiling are never reduced.

## Abilities

Abilities are one-shot identity rolls by default: each is decided once, at the first fusion that reaches its unlock level, and is never rerolled.

- `abilities.rollMode`: `'identity'` (default) or `'legacy'`.
- Unlock gates: `smartLock.minFusionCount` `1`, `explosive.emergent.minFusionCount` `5`, `elemental.minFusionCount` `9`.
- `abilities.maxActive` default `3`; `abilities.groups` prevents conflicting abilities.
- Single-roll chances: `explosive.emergent.baseChance` `0.35`, `elemental.baseChance` `0.30`, each scaled by `categoryChanceMultipliers`.
- `explosive.donorChance` (`1.0`): fusing a natively explosive donor reliably bestows Explosive Rounds.
- Potency scales with the gun's current fusion level (`abilities.powerScaling.perLevel` `0.05`, `maxMultiplier` `2.5`).
- `smartLock`: categories, mode roll, range curve, target priority, hostiles-only, and native skip IDs.

## Compatibility notes

- TaCZ APIs are version-sensitive. Pin TaCZ and test before pack release.
- Standard six attachment slots only.
- GunsmithLib airburst, proximity fuse, potion clouds, shields, and fire-control attachments are not yet inherited.
- TaCZ Attributes is not integrated yet.
- Single-player is the tested scope; kitbash is guarded off on dedicated servers by default.
