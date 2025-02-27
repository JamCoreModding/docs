_For an introduction to Totally Balanced Bone Drops, see the [About](about.md) page._

## For Players

If you are a player, you can configure TBBD via the configuration file. The configuration file is located at `config/tb-bone-drops.json`. It can also be edited via Mod Menu.

### Config Options

- `chance`
  - The chance that a bone will drop from an entity.
  - Default: `COMMON`
  - Options:
    - `VERY_RARE`
    - `RARE`
    - `COMMON`
    - `VERY_COMMON`
    - `ABUNDANT`

## For Developers, or Advanced Players

TBBD operates on a blacklist system. If a `LivingEntity` is not in the blacklist, it will drop a bone. The blacklist is in the form of an entity tag, located at `data/tb-bone-drops/tags/entity_type/blacklist.json`. You can use this to blacklist entities from dropping bones. 

### Default Entries

```json
{
  "replace": false,
  "values": [
    "minecraft:allay",
    "minecraft:armor_stand",
    "minecraft:bee",
    "minecraft:blaze",
    "minecraft:cave_spider",
    "minecraft:creeper",
    "minecraft:elder_guardian",
    "minecraft:ender_dragon",
    "minecraft:endermite",
    "minecraft:ghast",
    "minecraft:guardian",
    "minecraft:iron_golem",
    "minecraft:magma_cube",
    "minecraft:pufferfish",
    "minecraft:salmon",
    "minecraft:shulker",
    "minecraft:silverfish",
    "minecraft:slime",
    "minecraft:snow_golem",
    "minecraft:spider",
    "minecraft:tadpole",
    "minecraft:tropical_fish",
    "minecraft:vex",
    "minecraft:wither",
    "minecraft:wither_skeleton"
  ]
}
```
