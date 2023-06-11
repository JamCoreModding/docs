_For an introduction to Auto Recipe, see the [About](about.md) page._

Auto Recipe only supports the Quilt loader. It is not compatible with Fabric.

## Installation

Auto Recipe is available from [maven.jamalam.tech](https://maven.jamalam.tech/).
To find the latest version, see
[GitHub releases](https://github.com/JamCoreModding/auto-recipe).

```groovy
repositories {
    maven {
        url = "https://maven.jamalam.tech/"
    }
}

dependencies {
    modImplementation "io.github.jamalam360:autorecipe:VERSION"
    include "io.github.jamalam360:autorecipe:VERSION"
}
```

Auto Recipe is intended to be JiJ'd into your mod, so is not available from
Modrinth or CurseForge.

## Usage

To use Auto Recipe, you must first create a recipe class:

```java
public class TestRecipe extends AutoSerializedRecipe<Inventory> {

    @RecipeVar
    ItemStack input;
    @RecipeVar
    ItemStack output;
    /* `@RecipeVar` infers the vars name from the field name, but it can be explicitly specified:  */
    @RecipeVar("time")
    int processingTime;

    /* Your recipe functions  (i.e. craft, matches, etc.), as usual */
}
```

Once you have created your recipe class, you must register it with Auto Recipe
in your mod initializer:

```java
RecipeType<TestRecipe> test = AutoRecipeRegistry.registerRecipeSerializer(new Identifier("mymod","test"), TestRecipe::new);
```

That's it! No more boilerplate or having to write recipe serializers yourself.
It's easy to use your recipe type (`/data/mymod/recipes/test_recipe.json`):

```json
{
  "type": "mymod:test",
  "input": "minecraft:stone",
  "output": {
    "item": "minecraft:cobblestone",
    "count": 2
  },
  "time": 44
}
```

## Types

Auto Recipe supports (de)serialization of many common types out of the box,
including:

- Java primitives
- Strings
- Lists
- Maps
  - Keys must be strings, or a type that has a constructor that takes a string
    (e.g `Identifier`)
- Common Minecraft classes
  - E.g. `ItemStack`, `Ingredient`

If you need to serialize a type that isn't supported out of the box, you can
register a custom serializer:

```java
AutoRecipeRegistry.registerVariableSerializer(String namespace, Class<T> clazz, RecipeVarSerializer<T> serializer)
```

- `namespace` is usually your mod ID.
- `clazz` is the class of the type you want to serialize.
- `serializer` is a `RecipeVarSerializer` that can serialize and deserialize the
  type. You can use your IDE's auto-complete to find the methods you need to
  implement.

This serializer only applies to recipes in the specified namespace. If you want
to register a serializer that applies to all recipes, use
`AutoRecipeRegistry.registerGlobalVariableSerializer`, but be careful - this can
break other mods.
