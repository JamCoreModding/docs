RightClickHarvest is available on [my maven](https://maven.jamalam.tech). You
can check versions by browsing the maven.

```groovy
repositories {
    maven {
        url "https://maven.jamalam.tech/"
    }
}

dependencies {
    // for fabric and quilt
    modImplementation("io.github.jamalam360:right-click-harvest:<VERSION>")
    // for forge
    implementation fg.deobf("io.github.jamalam360:right-click-harvest:<VERSION>")
}
```
