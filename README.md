
A [maven](http://maven.apache.org/) plugin to generate UML diagrams using [PlantUML](http://plantuml.sourceforge.net/) syntax.
[ ![Download](https://api.bintray.com/packages/jmdesprez/maven/plantuml-maven-plugin/images/download.svg) ](https://bintray.com/jmdesprez/maven/plantuml-maven-plugin/_latestVersion)

# Usage

To generate images from PlantUML description add following dependency to your pom.xml:

```xml
...
<build>
  <plugins>
    <plugin>
      <groupId>com.github.jmdesprez</groupId>
	  <artifactId>plantuml-maven-plugin</artifactId>
	  <version>1.4-SNAPSHOT</version>
      <configuration>
        <sourceFiles>
          <directory>${basedir}</directory>
          <truncatePattern>src/main/*</truncatePattern>
          <includes>
            <include>src/main/plantuml/**/*.txt</include>
          </includes>
        </sourceFiles>
      </configuration>
      <dependencies>
        <dependency>
          <groupId>net.sourceforge.plantuml</groupId>
          <artifactId>plantuml</artifactId>
          <version>1.2019.11</version>
        </dependency>
      </dependencies>
    </plugin>
  </plugins>
</build>
```

Note that you must explicitely define the PlantUML version you want to use.

Then execute command:

```
mvn clean com.github.jmdesprez:plantuml-maven-plugin:generate
```

# Extra configuration options

`outputDirectory` Directory where generated images are generated. Defaults to `${basedir}/target/plantuml`

`outputInSourceDirectory` Whether or not to generate images in same directory as the source file. Defaults to `false`.

`format` Output format. Defaults to `png`.

`verbose` Wether or not to output details during generation. Defaults to `false`.


Released under [Apache 2 license](http://www.apache.org/licenses/LICENSE-2.0.html).
