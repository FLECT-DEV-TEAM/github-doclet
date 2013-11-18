# Github Doclet

A custom doclet each class pages have link to github.

## Usage
### javadoc command
Use javadoc command with following parameters.

- docletpath - Path to githubDoclet-1.0.jar
- doclet - jp.co.flect.doclets.github.Standard
- github - Path to github source(e.g. https://github.com/shunjikonishi/flectCommon/tree/master/src/main/java)

### Maven
Add following repository and plugin.

    <repositories>
        <repository>
            <id>flect</id>
            <name>flect</name>
            <url>http://flect.github.io/maven-repo/</url>
        </repository>
    </repositories>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-javadoc-plugin</artifactId>
                <version>2.9.1</version>
                <configuration>
                    <doclet>jp.co.flect.doclets.github.Standard</doclet>
                    <docletArtifact>
                        <groupId>jp.co.flect</groupId>
                        <artifactId>githubDoclet</artifactId>
                        <version>1.0</version>
                    </docletArtifact>
                    <additionalparam>-github https://github.com/[YOUR USERNAME]/[YOUR REPOSITORY]/tree/master/src/main/java</additionalparam>
                    <useStandardDocletOptions>true</useStandardDocletOptions>
                </configuration>
            </plugin>
        </plugins>
    </build>
