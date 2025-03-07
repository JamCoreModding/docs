Sort It Out! has a resource-pack driven system for modifying where sort buttons are displayed for different screens.

By default, Sort It Out! provides definitions for vanilla containers, and some modded containers. If no definition is present for a screen, the mod attempts to add a default position button for sorting the player inventory.

## Adding a Custom Definition

> If you are adding a definition, please consider contributing it to Sort It Out! directly or suggesting it on the [GitHub page](https://github.com/JamCoreModding/sort-it-out). This guide assumes a basic familiarity with creating resource packs, and with using Linkie. If you are unfamiliar with either, please ask on the Discord or the GitHub page.

Sort button defitions are split into two parts: the type predicate, which defines what screen the definition applies to, and the button definitions, which defines where sort buttons should appear and what inventories they should sort.

First, create a resource (not data) pack and add the file `<your resource pack namespace>/sort_buttons/<arbritrary name for your sort button definition>.json`.

Open Minecraft and run `/sortitoutc toggle_slot_index_debug_renderer`, then open the container/screen you want to add sort buttons to. This shows the index of each slot, along with a class name for the screen (starting `net.minecraft.`) and a resource location (like `minecraft:inventory`, or `null`). If the resource location is `null`, the type predicate will need to refer to the screen by class. To do this, you need to know the fully-qualified mojmap and intermediary names for the screen. Use [Linkie](https://linkie.shedaniel.me) for this (this tutorial is not a Linkie guide, however).

The JSON file should then be filled in like so:

```json
{
	// If the resource location was not null, use the following:
	"type": "<resource location>",
	// Otherwise, use this `type`:
	"type": {
		"mojmap": "<mojmap class name>",
		"intermediary": "<intermediary class name>"
	},
	// Then, add your sort button definitions
	"sortButtons": [
		{
			"xOffset": 12, // x offset from the left-hand side of the screen
			"yOffset": 10, // y offset from the top of the screen (positive down)
			"slotStartIndex": 0 // an index of any slot in the inventory section that this button should sort.
		},
		// repeat as many times as you like to add more sort buttons
	]
}
```

To remove the default sort buttons for a screen, just set `sortButtons` to an empty array (`[]`).

