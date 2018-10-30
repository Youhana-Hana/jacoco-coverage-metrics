# jacoco-coverage-metrics
Parent POM file to define Java jacoco coverage thresholds.

# Description
Enable code coverage check, you need to use `coverage-root` as parent, from version (1.0.0), in your pom.xml file as follow:
``` xml
<parent>
    <groupId>it.sdp</groupId>
    <artifactId>sdp-root</artifactId>
    <version>1.2.0</version>
</parent>
```

All properties defined in the project as 75% with 0 missed classes, this will not work with current projects coverage, in order to increase code coverage gradually, override the parent properties with the following one:
``` xml
<properties>
    <jacoco.class.cover.ratio>0.2</jacoco.class.cover.ratio>
    <jacoco.method.cover.ratio>0.2</jacoco.method.cover.ratio>
    <jacoco.line.cover.ratio>0.2</jacoco.line.cover.ratio>
    <jacoco.instructions.cover.ratio>0.2</jacoco.instructions.cover.ratio>
    <jacoco.instructions.cover.missed.classes.count>10</jacoco.instructions.cover.missed.classes.count>
    <jacoco.instructions.cover.ratio.it>0.2</jacoco.instructions.cover.ratio.it>
    <jacoco.instructions.cover.missed.classes.count.it>10</jacoco.instructions.cover.missed.classes.count.it>
</properties>
```

# Common commands:
## Run unit tests: 
``` bash
mvn clean verify -DskipITs
```

## Run integration tests: 
``` bash
mvn clean verify -DskipUnitTests
```

## Run smoke tests:
``` bash
mvn clean test -Dgroups="smoke.Smoke"
```

# Check code coverage reports
Unit tests report  at target\site\jacoco-ut\index.html

Integration tests report at target\site\jacoco-it\index.html
