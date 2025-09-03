# Maveniverse Maven-BOMs

The build uses Nisse for "complete CI friendly" setup. See contents of `build.properties`.

This file is single place that contains the version of Maven to generate BOMs for, and 
is also used in resulting artifact versions as well.

## Releasing

Due use of Nisse and Bom Builder (both rewrite plugins), the release procedure is currently
manual:
* set versions in POM to `-SNAPSHOT`-less
* `mvn deploy -P maveniverse-release -Dnjord.autoPublish` -> this stages project to Central Portal
* if validation OK, on Portal start publishing
* tag release
* set versions in POM to `-02-SNAPSHOT` (increment counter)
* push all w/ tags

Currently work happens on branches:
* maven-3.9.x is for Maven 3.9.x line
