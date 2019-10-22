# SurefirePluginBDD


-<plugins>

<!-- during the test phase of the build lifecycle to execute the unit tests -->



-<plugin>

<groupId>org.apache.maven.plugins</groupId>

<artifactId>maven-surefire-plugin</artifactId>

<version>3.0.0-M3</version>


-<configuration>


-<includes>

<include>**/*SmokeRunner.java</include>

</includes>

<testFailureIgnore>true</testFailureIgnore>

</configuration>

</plugin>


-<plugin>

<groupId>net.masterthought</groupId>

<artifactId>maven-cucumber-reporting</artifactId>

<version>4.7.0</version>


-<executions>


-<execution>

<id>execution</id>

<phase>verify</phase>


-<goals>

<goal>generate</goal>

</goals>


-<configuration>

<projectName>name_of_project</projectName>

<!-- output directory for the generated report -->


<outputDirectory>${project.build.directory}</outputDirectory>

<!-- optional, defaults to outputDirectory if not specified -->


<inputDirectory>${project.build.directory}</inputDirectory>


-<jsonFiles>

<!-- supports wildcard or name pattern -->


<param>**/*.json</param>

</jsonFiles>

</configuration>

</execution>

</executions>

</plugin>

</plugins>

</build>
