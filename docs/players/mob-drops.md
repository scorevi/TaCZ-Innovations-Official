# Mob Ammo Drops for Players

Mob Ammo Drops keeps you supplied by making hostile mobs drop ammo for the guns you actually carry.

## When it triggers

- A hostile mob dies
- You are carrying at least one TaCZ gun with a real ammo type
- The mob is killed in a way that respects normal mob loot rules

The base drop chance is `25%`.

## What influences the drop

- The caliber of the gun in your hand is favored.
- Calibers with low reserves get a strong boost.
- Calibers you are already stockpiling are deprioritized.
- Backpacks, shulkers, and Curios can count toward your carried guns and reserves.
- Infinite-reload guns are treated as self-sustaining and do not hog the ammo pool.

## What you receive

A stack of the correct ammo item for one of your carried guns. Amounts scale with magazine size and are capped to avoid flooding your inventory.

Single-shot weapons still receive a small usable drop instead of one round or nothing.

## Practical tips

- Carry the gun whose ammo you want to find.
- If a caliber is already well stocked, expect other calibers to drop instead.
- Fused guns count as normal carried guns; their ammo type is read from the chassis.
