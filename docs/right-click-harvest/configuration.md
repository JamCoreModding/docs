The configuration file is located at `config/rightclickharvest.json5`. It can also be edited via the mod menu.

If you are a modpack or mod author, you may be interested in the [tags](/right-click-harvest/tags) or [API](/right-click-harvest/api)

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
