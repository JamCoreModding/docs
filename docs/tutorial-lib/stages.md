Tutorial Lib contains several out of the box stages (see the package
`io.github.jamalam360.tutorial.lib.stage`), but you may need to implement your
own.

If you wish to do this:

1. Create a class extending `Stage` that holds any required state (such as an `Item` or an `Identifier`)
2. In a relevant place (such as an event or mixin which will trigger your stage), do the following:
```java
if (YourMod.YOUR_TUTORIAL.getCurrentStage() instanceof YourStage && /* check logic */) {
    YourMod.YOUR_TUTORIAL.advanceStage();
}
```
