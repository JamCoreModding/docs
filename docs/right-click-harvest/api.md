RightClickHarvest provides a simple API currently composed of a single event.

## Adding RightClickHarvest to Your Project

=== "Architectury"

	=== "Using Gradle Properties"

		``` toml title="gradle.properties"
		# rest of properties file ...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib_version=1.0.1
		# find this at https://github.com/JamCoreModding/right-click-harvest/releases
		rightclickharvest_version=4.0.1
		```

		``` groovy title="build.gradle"
		allprojects {
			repositories {
				// rest of repositories block...

				maven {
					name = "Jamalam's Maven"
					url = "https://maven.jamalam.tech/releases"

					content {
						includeGroup "io.github.jamalam360"
					}
				}
			}
		}
		```

		``` groovy title="common/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:right-click-harvest:${rightclickharvest_version}"
			modRuntimeOnly "io.github.jamalam360:jamlib:${jamlib_version}"
		}
		```

		``` groovy title="fabric/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:right-click-harvest-fabric:${rightclickharvest_version}"
			modRuntimeOnly "io.github.jamalam360:jamlib-fabric:${jamlib_version}"
		}
		```

		``` groovy title="forge/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:right-click-harvest-forge:${rightclickharvest_version}"
			modRuntimeOnly "io.github.jamalam360:jamlib-forge:${jamlib_version}"
			// Dependency of JamLib. Forge requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

		``` groovy title="quilt/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:right-click-harvest-quilt:${rightclickharvest_version}"
			modRuntimeOnly "io.github.jamalam360:jamlib-quilt:${jamlib_version}"
		}
		```

	=== "Using Version Catalogues"

		``` toml title="Version Catalogue"
		[versions]
		# rest of versions...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib = "1.0.1"
		# find this at https://github.com/JamCoreModding/right-click-harvest/releases
		rightclickharvest = "4.0.1"

		[libraries]
		# rest of libraries...
		jamlib-common = { module = "io.github.jamalam360:jamlib", version.ref = "jamlib" }
		jamlib-fabric = { module = "io.github.jamalam360:jamlib-fabric", version.ref = "jamlib" }
		jamlib-quilt = { module = "io.github.jamalam360:jamlib-quilt", version.ref = "jamlib" }
		jamlib-forge = { module = "io.github.jamalam360:jamlib-forge", version.ref = "jamlib" }
		rightclickharvest-common = { module = "io.github.jamalam360:right-click-harvest", version.ref = "rightclickharvest" }
		rightclickharvest-fabric = { module = "io.github.jamalam360:right-click-harvest-fabric", version.ref = "rightclickharvest" }
		rightclickharvest-quilt = { module = "io.github.jamalam360:right-click-harvest-quilt", version.ref = "rightclickharvest" }
		rightclickharvest-forge = { module = "io.github.jamalam360:right-click-harvest-forge", version.ref = "rightclickharvest" }
		```

		``` groovy title="build.gradle"
		allprojects {
			repositories {
				// rest of repositories block...

				maven {
					name = "Jamalam's Maven"
					url = "https://maven.jamalam.tech/releases"

					content {
						includeGroup "io.github.jamalam360"
					}
				}
			}
		}
		```

		``` groovy title="common/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation libs.rightclickharvest.common
			modRuntimeOnly libs.jamlib.common
		}
		```

		``` groovy title="fabric/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation libs.rightclickharvest.fabric
			modRuntimeOnly libs.jamlib.fabric
		}
		```

		``` groovy title="forge/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation libs.rightclickharvest.forge
			modRuntimeOnly libs.jamlib.forge
			// Dependency of JamLib. Forge requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

		``` groovy title="quilt/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation libs.rightclickharvest.quilt
			modRuntimeOnly libs.jamlib.quilt
		}
		```

=== "Fabric"

	=== "Using Gradle Properties"

		``` toml title="gradle.properties"
		# rest of properties file ...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib_version=1.0.1
		# find this at https://github.com/JamCoreModding/right-click-harvest/releases
		rightclickharvest_version=4.0.1
		```

		``` groovy title="build.gradle"
		repositories {
			// rest of repositories block...

			maven {
				name = "Jamalam's Maven"
				url = "https://maven.jamalam.tech/releases"

				content {
					includeGroup "io.github.jamalam360"
				}
			}
		}

		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:right-click-harvest-fabric:${rightclickharvest_version}"
			modRuntimeOnly "io.github.jamalam360:jamlib-fabric:${jamlib_version}"
		}
		```

	=== "Using Version Catalogues"

		``` toml title="Version Catalogue"
		[versions]
		# rest of versions...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib = "1.0.1"
		# find this at https://github.com/JamCoreModding/right-click-harvest/releases
		rightclickharvest = "4.0.1"

		[libraries]
		# rest of libraries...
		jamlib = { module = "io.github.jamalam360:jamlib-fabric", version.ref = "jamlib" }
		rightclickharvest = { module = "io.github.jamalam360:right-click-harvest-fabric", version.ref = "rightclickharvest" }
		```

		``` groovy title="build.gradle"
		repositories {
			// rest of repositories block...

			maven {
				name = "Jamalam's Maven"
				url = "https://maven.jamalam.tech/releases"

				content {
					includeGroup "io.github.jamalam360"
				}
			}
		}

		dependencies {
			// rest of dependencies block...

			modImplementation libs.rightclickharvest
			modRuntimeOnly libs.jamlib
		}
		```

=== "Quilt"

	=== "Using Gradle Properties"

		``` toml title="gradle.properties"
		# rest of properties file ...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib_version=1.0.1
		# find this at https://github.com/JamCoreModding/right-click-harvest/releases
		rightclickharvest_version=4.0.1
		```

		``` groovy title="build.gradle"
		repositories {
			// rest of repositories block...

			maven {
				name = "Jamalam's Maven"
				url = "https://maven.jamalam.tech/releases"

				content {
					includeGroup "io.github.jamalam360"
				}
			}
		}

		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:right-click-harvest-quilt:${rightclickharvest_version}"
			modRuntimeOnly "io.github.jamalam360:jamlib-quilt:${jamlib_version}"
		}
		```

	=== "Using Version Catalogues"

		``` toml title="Version Catalogue"
		[versions]
		# rest of versions...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib = "1.0.1"
		# find this at https://github.com/JamCoreModding/right-click-harvest/releases
		rightclickharvest = "4.0.1"

		[libraries]
		# rest of libraries...
		jamlib = { module = "io.github.jamalam360:jamlib-quilt", version.ref = "jamlib" }
		rightclickharvest = { module = "io.github.jamalam360:right-click-harvest-quilt", version.ref = "rightclickharvest" }
		```

		``` groovy title="build.gradle"
		repositories {
			// rest of repositories block...

			maven {
				name = "Jamalam's Maven"
				url = "https://maven.jamalam.tech/releases"

				content {
					includeGroup "io.github.jamalam360"
				}
			}
		}

		dependencies {
			// rest of dependencies block...

			modImplementation libs.rightclickharvest
			modRuntimeOnly libs.jamlib
		}
		```

=== "Forge"

	=== "Using Gradle Properties"

		``` toml title="gradle.properties"
		# rest of properties file ...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib_version=1.0.1
		# find this at https://github.com/JamCoreModding/right-click-harvest/releases
		rightclickharvest_version=4.0.1
		```

		``` groovy title="build.gradle"
		repositories {
			// rest of repositories block...

			maven {
				name = "Jamalam's Maven"
				url = "https://maven.jamalam.tech/releases"

				content {
					includeGroup "io.github.jamalam360"
				}
			}
		}

		dependencies {
			// rest of dependencies block...

			implementation fg.deobf("io.github.jamalam360:right-click-harvest-forge:${jamlib_version}")
			runtimeOnly fg.deobf("io.github.jamalam360:jamlib-forge:${jamlib_version}")
			// Dependency of JamLib. Forge requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

	=== "Using Version Catalogues"

		``` toml title="Version Catalogue"
		[versions]
		# rest of versions...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib = "1.0.1"
		# find this at https://github.com/JamCoreModding/right-click-harvest/releases
		rightclickharvest = "4.0.1"

		[libraries]
		# rest of libraries...
		jamlib = { module = "io.github.jamalam360:jamlib-forge", version.ref = "jamlib" }
		rightclickharvest = { module = "io.github.jamalam360:right-click-harvest-forge", version.ref = "rightclickharvest" }
		```

		``` groovy title="build.gradle"
		repositories {
			// rest of repositories block...

			maven {
				name = "Jamalam's Maven"
				url = "https://maven.jamalam.tech/releases"

				content {
					includeGroup "io.github.jamalam360"
				}
			}
		}

		dependencies {
			// rest of dependencies block...

			implementation fg.deobf(libs.rightclickharvest)
			runtimeOnly fg.deobf(libs.jamlib)
			// Dependency of JamLib. Forge requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

Once RightClickHarvest is successfully in your development environment, you can add a dependency on it to your mod metadata. You can also make this optional if you wish.

=== "Fabric"

	``` json title="fabric.mod.json"
	{
		// rest of JSON
		"depends": {
			// rest of depends
			"rightclickharvest": ">=1.0.0"
		}
	}
	```

=== "Quilt"

	``` json title="quilt.mod.json"
	{
		// rest of JSON
		"quilt_loader": {
			// rest of quilt_loader
			"depends": [
				// rest of depends
				{
					"id": "rightclickharvest",
					"version": ">=1.0.0"
				}
			]
		}
	}
	```

=== "Forge"

	``` toml title="META-INF/mods.toml"
	[[dependencies.YOUR_MOD_ID]]
	modId = "rightclickharvest"
	mandatory = true
	versionRange = "[1.0.0,)"
	ordering = "AFTER"
	side = "BOTH"
	```

## Events

Now that RightClickHarvest is added, you can use its events.

### AfterHarvest

This event is called after a successful harvest.

=== "Fabric or Quilt"

	``` java title="Your Mod Initializer"
	RightClickHarvestFabricLikeCallbacks.AFTER_HARVEST.register((ctx) -> { ... });
	```

=== "Forge"

	``` java title="In an Event Subscribed Class"
	@SubscribeEvent
	public static void onAfterHarvest(RightClickHarvestForgeEvents.AfterHarvest ev) {
		HarvestContext ctx = ev.getContext();
		...
	}
	```
