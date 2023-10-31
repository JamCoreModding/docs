![Supported on Quilt](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@2/assets/cozy/supported/quilt_vector.svg)
![Supported on Fabric](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@2/assets/cozy/supported/fabric_vector.svg)
![Supported on Forge](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@2/assets/cozy/supported/forge_vector.svg)
[![Available on Modrinth](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@2/assets/cozy/available/modrinth_vector.svg)](https://modrinth.com/mod/jamlib)
[![Available on CurseForge](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@2/assets/cozy/available/curseforge_vector.svg)](https://www.curseforge.com/minecraft/mc-mods/jamlib)
[![Available on GitHub](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@2/assets/cozy/available/github_vector.svg)](https://github.com/JamCoreModding/jamlib)

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

		``` groovy title="forge/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:jamlib-forge:${jamlib_version}"
			// Dependency of JamLib. Forge requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

		``` groovy title="quilt/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation "io.github.jamalam360:jamlib-quilt:${jamlib_version}"
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
		jamlib-quilt = { module = "io.github.jamalam360:jamlib-quilt", version.ref = "jamlib" }
		jamlib-forge = { module = "io.github.jamalam360:jamlib-forge", version.ref = "jamlib" }
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

		``` groovy title="forge/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation libs.jamlib.forge
			// Dependency of JamLib. Forge requires that we specify this
			forgeRuntimeLibrary "blue.endless:jankson:1.2.3"
		}
		```

		``` groovy title="quilt/build.gradle"
		dependencies {
			// rest of dependencies block...

			modImplementation libs.jamlib.quilt
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

=== "Quilt"

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

			modImplementation "io.github.jamalam360:jamlib-quilt:${jamlib_version}"
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
		jamlib = { module = "io.github.jamalam360:jamlib-quilt", version.ref = "jamlib" }
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

=== "Forge"

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

			implementation fg.deobf("io.github.jamalam360:jamlib-forge:${jamlib_version}")
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
		jamlib = { module = "io.github.jamalam360:jamlib-forge", version.ref = "jamlib" }
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

=== "Quilt"

	``` json title="quilt.mod.json"
	{
		// rest of JSON
		"quilt_loader": {
			// rest of quilt_loader
			"depends": [
				// rest of depends
				{
					"id": "jamlib",
					"version": ">=1.0.0"
				}
			]
		}
	}
	```

=== "Forge"

	``` toml title="META-INF/mods.toml"
	[[dependencies.YOUR_MOD_ID]]
	modId = "jamlib"
	mandatory = true
	versionRange = "[1.0.0,)"
	ordering = "AFTER"
	side = "BOTH"
	```

Refer to the sidebar for documentation on the available APIs within JamLib.
