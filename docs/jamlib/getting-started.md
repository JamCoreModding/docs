JamLib is a set of cross-platform APIs developed with Architectury that we use for all of our mods.

You are also free to use JamLib in your projects, hence we have created this documentation on it.

## Features

- JSON5 configuration with automatic config screens.

## Adding JamLib to Your Project

=== "Architectury"

	=== "Using Gradle Properties"

		``` toml title="gradle.properties"
		# rest of properties file ...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib_version=1.0.1
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

			modImplementation "io.github.jamalam360:jamlib:${jamlib_version}"
		}
		```

		``` groovy title="fabric/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:jamlib-fabric:${jamlib_version}"
		}
		```

		``` groovy title="neoforge/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:jamlib-forge:${jamlib_version}"
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

		[libraries]
		# rest of libraries...
		jamlib-common = { module = "io.github.jamalam360:jamlib", version.ref = "jamlib" }
		jamlib-fabric = { module = "io.github.jamalam360:jamlib-fabric", version.ref = "jamlib" }
		jamlib-neoforge = { module = "io.github.jamalam360:jamlib-neoforge", version.ref = "jamlib" }
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

			modImplementation libs.jamlib.common
		}
		```

		``` groovy title="fabric/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation libs.jamlib.fabric
		}
		```

		``` groovy title="neoforge/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation libs.jamlib.neoforge
			// Dependency of JamLib. NF requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

=== "Fabric"

	=== "Using Gradle Properties"

		``` toml title="gradle.properties"
		# rest of properties file ...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib_version=1.0.1
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

			modImplementation "io.github.jamalam360:jamlib-fabric:${jamlib_version}"
		}
		```

	=== "Using Version Catalogues"

		``` toml title="Version Catalogue"
		[versions]
		# rest of versions...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib = "1.0.1"

		[libraries]
		# rest of libraries...
		jamlib = { module = "io.github.jamalam360:jamlib-fabric", version.ref = "jamlib" }
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

			modImplementation libs.jamlib
		}
		```

=== "NeoForge"

	=== "Using Gradle Properties"

		``` toml title="gradle.properties"
		# rest of properties file ...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib_version=1.0.1
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

			implementation fg.deobf("io.github.jamalam360:jamlib-neoforge:${jamlib_version}")
			// Dependency of JamLib. NF requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

	=== "Using Version Catalogues"

		``` toml title="Version Catalogue"
		[versions]
		# rest of versions...
		# find this at https://github.com/JamCoreModding/jamlib/releases
		jamlib = "1.0.1"

		[libraries]
		# rest of libraries...
		jamlib = { module = "io.github.jamalam360:jamlib-neoforge", version.ref = "jamlib" }
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

			implementation fg.deobf(libs.jamlib)
			// Dependency of JamLib. NF requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

Once JamLib is successfully in your development environment, you can add a dependency on it to your mod metadata.

=== "Fabric"

	``` json title="fabric.mod.json"
	{
		// rest of JSON
		"depends": {
			// rest of depends
			"jamlib": ">=1.0.0"
		}
	}
	```

=== "NeoForge"

	``` toml title="META-INF/neoforge.mods.toml"
	[[dependencies.YOUR_MOD_ID]]
	modId = "jamlib"
	mandatory = true
	versionRange = "[1.0.0,)"
	ordering = "AFTER"
	side = "BOTH"
	```

Refer to the sidebar for documentation on the available APIs within JamLib.
