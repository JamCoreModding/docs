_For an introduction to Utility Belt, see the [About](about.md) page._

## For Players

If you are a player, you can configure Utility Belt via the configuration file.
The configuration file is located at `config/utilitybelt.json`. It can also be
edited via Mod Menu.

### Config Options

- `isScrollingInverted`
    - Whether scrolling up or down will cycle through the belt in the opposite
      direction.
    - Default: `false`
- `displayUtilityBeltWhenNotSelected`
    - Whether the utility belt hotbar will be displayed when it is not selected.
    - Default: `true`
- `hotbarKeyBehaviour`
    - What happens when a 'hotbar key' (i.e. 1-9, to select the vanilla hotbar
    slots) is pressed.
    - Default: `SWITCH_BELT_SLOT`
    - Options:
        - `SWITCH_BELT_SLOT`
            - Switches to the corresponding belt slot.
        - `SWITCH_BACK_TO_HOTBAR`
            - Switches back to the vanilla hotbar.

## For Developers, or Advanced Players

Utility Belt contains an item tag, `utilitybelt:allowed_in_utility_belt`. The
utility belt accepts all items that inherit from `ToolItem`, as well as those in
this tag. If you want to add an item to the utility belt, add it to this tag
(`/data/utilitybelt/tags/items/allowed_in_utility_belt.json`).

### Default Entries

```json
{
  "replace": false,
  "values": []
}
```
