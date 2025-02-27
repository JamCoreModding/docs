_For an introduction to Utility Belt, see the [About](about.md) page._

## For Players

If you are a player, you can configure Utility Belt via the configuration file.
The configuration file is located at `config/utility_belt.json5`. It can also be
edited via Mod Menu or the (Neo)Forge config screen.

Available options are documented in comments or tooltips.

## For Developers, or Pack Makers

Utility Belt contains an item tag, `utility_belt:allowed_in_utility_belt`. The
utility belt accepts several items by Java class (namely `TieredItem`, `Brush`, etc.), as well as those in
this tag. If you want to add an item to the utility belt, add it to this tag
(`/data/utility_belt/tags/item/allowed_in_utility_belt.json`).

