JamLib comes with a simple checker that is able to determine if a mod file looks like it has been downloaded from a repost site.

If you are using our template mod, this works out of the box. Otherwise, you will need to make sure your JAR has a `JamLib-File-Name` attribute in its manifest that contains the original file name of the JAR, including the `.jar` extension:

```kotlin
jar {
  manifest {
    attributes([
	  'JamLib-File-Name'      : "my-cool-mod-${rootProject.version}.jar", (1)
	])
  }
}
```

1. Remember to replace `my-cool-mod` with your JAR name.

You then need to call the method from your main mod initializer (in the common initializer, if you are using a multiloader toolchain):

```java
JamLib.checkForJarRenaming(YourMainClass.class);
```

Everything else, including notifying the user, will be handled automatically.

Sites such as 9minecraft are known to rename jars, so if a user is caught with one such jar they will be notified _once_ per jar.