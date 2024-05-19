## Block Tags

- `blacklist`: blocks that RightClickHarvest should completely ignore.
- `radius_harvest_blacklist`: blocks that are ignored by the harvest in
  radius feature (e.g. cocoa beans).
- `hoe_never_required`: blocks that never require a hoe to be harvested,
  even if `Config.requireHoe` is true (e.g. nether wart and cocoa beans).

## Item Tags

These tags are used to determine the radius when harvesting in a radius.

- `low_tier_hoes`: hoes that are equivalent to iron hoes.
- `mid_tier_hoes`: hoes that are equivalent to diamond and gold hoes.
- `high_tier_hoes`: hoes that are equivalent to Netherite hoes.

If a hoe is not included in any of these tags, it will be considered to be
equivalent to a wooden hoe.
