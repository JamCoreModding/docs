_For an introduction to RightClickHarvest, see the [About](about.md) page._

## For Players

If you are a player, you can configure RightClickHarvest via the configuration file. The configuration file is located at `config/right-click-harvest.json` (`.toml` on Forge). It can also be edited via Mod Menu.

### Config Options

- `requireHoe`
  - Whether to require the player holds a hoe to right-click-harvest a crop.
  - Default: `true`
  - Options:
    - `false`
    - `true`
- `harvestInRadius`
  - Whether to increase the radius of crops that are harvested if a higher tier hoe is used.
  - Default: `true`
  - Options:
    - `false`
    - `true`
- `hungerLevel`
  - The amount of hunger to use when harvesting crops, if any.
  - Default: `NORMAL`
  - Options:
    - `NONE`
    - `LOW`
    - `NORMAL`
    - `HIGH`
