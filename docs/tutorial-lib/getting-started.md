_For an introduction to Tutorial Lib, see the [About](about.md) page._

## Installation

Auto Recipe is available from [maven.jamalam.tech](https://maven.jamalam.tech/).
To find the latest version, see
[GitHub releases](https://github.com/JamCoreModding/tutorial-lib).

```groovy
repositories {
    maven {
        url = "https://maven.jamalam.tech/"
    }
}

dependencies {
    modImplementation "io.github.jamalam360:tutorial-lib:VERSION"
    include "io.github.jamalam360:tutorial-lib:VERSION"
}
```

Tutorial Lib is intended to be JiJ'd into your mod, so is not available from
Modrinth or Curseforge.

## Usage

To use Tutorial Lib you must create an instance of `Tutorial`:

```java
// The texture must be 256x256.
public static final Identifier TEX = new Identifier("your_mod", "textures/gui/toast.png");
public static final Tutorial TUTORIAL = new Tutorial(
  new ObtainItemStage(
    Items.LEATHER_HELMET,
    new CustomTutorialToast(
      TEX,
      0, // u (i.e. x offset from top left of texture)
      0, // v (i.e. y offset from top left of texture)
      Text.translatable("tutorial.your_mod.stage_one.title")
    )
  ),
  new EquipItemStage(
    Items.LEATHER_HELMET,
    new CustomTutorialToast(
      TEX,
      20,
      0,
      Text.translatable("tutorial.your_mod.stage_two.title"),
      Text.translatable("tutorial.your_mod.stage_two.description")
    )
  )
);
```

Hopefully this is fairly self explanatory; the user obtains a leather helmet,
and the `tutorial.your_mod.stage_one.title` toast is displayed, the user equips
the leather helmet, and the second toast is displayed. Once you have created
your tutorial, you must register it in your mod initializer:

```java
Registry.register(TutorialLib.TUTORIAL_REGISTRY, new Identifier("your_mod", "tutorial"), TUTORIAL);
```

The tutorial will then automatically trigger and begin when the user obtains the
leather helmet. The current stage of the tutorial is stored in `options.txt`
(but is hidden from the options screen).
