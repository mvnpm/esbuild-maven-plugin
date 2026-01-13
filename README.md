# esbuild-maven-plugin

[![Build Status](https://img.shields.io/github/actions/workflow/status/mvnpm/esbuild-maven-plugin/maven.yml?label=Build&branch=main)](https://github.com/mvnpm/esbuild-maven-plugin/actions/workflows/maven.yml)
[![Usefulness 100%](https://img.shields.io/badge/usefulness-100%25-success.svg?label=Usefulness)](https://www.google.com/search?q=pasta+machine)
[![Maven Central](https://img.shields.io/maven-central/v/io.mvnpm/esbuild-maven-plugin.svg?label=Maven%20Central)](https://search.maven.org/artifact/io.mvnpm/esbuild-maven-plugin)
[![License](https://img.shields.io/github/license/apache/maven.svg?label=License)](https://www.apache.org/licenses/LICENSE-2.0)

A **Maven plugin** that integrates [esbuild](https://esbuild.github.io/) into your Java project for fast and modern JavaScript/TypeScript/CSS/SCSS bundling.

---

## Features
- Runs **esbuild** during Maven build lifecycle.
- Supports Maven dependencies for web assets via [mvnpm](https://mvnpm.org/).
- Configurable source/output directories and entry point.
- No Node.js installation required — uses Maven dependencies.

---

## Quick Start

Add the plugin to your `pom.xml`:

```xml
<plugin>
    <groupId>io.mvnpm</groupId>
    <artifactId>esbuild-maven-plugin</artifactId>
    <version>2.0.0.CR2</version>
    <executions>
        <execution>
            <id>esbuild</id>
            <goals>
                <goal>esbuild</goal>
            </goals>
        </execution>
    </executions>
    <configuration>
        <entryPoint>backoffice.js</entryPoint>
    </configuration>
    <dependencies>
        <!-- Web dependencies using mvnpm.io -->
        <dependency>
            <groupId>org.mvnpm</groupId>
            <artifactId>bootstrap</artifactId>
            <version>5.3.3</version>
        </dependency>
        <dependency>
            <groupId>org.mvnpm.at.popperjs</groupId>
            <artifactId>core</artifactId>
            <version>2.11.8</version>
        </dependency>
        <dependency>
            <groupId>org.mvnpm</groupId>
            <artifactId>bootstrap-icons</artifactId>
            <version>1.11.3</version>
        </dependency>
    </dependencies>
</plugin>
```

---

## Configuration Options

| Parameter        | Default                                                   | Description                          |
|------------------|-----------------------------------------------------------|--------------------------------------|
| `sourceDirectory`| `src/main/web`                                           | Directory containing source files.  |
| `outputDirectory`| `target/classes/META-INF/resources/static/bundle`        | Output directory for bundled files. |
| `entryPoint`     | `index.js`                                               | Main JS entry point.                |
| `nodeModules`    | `node_modules`                                           | Node modules directory.             |

---

## License
[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0)
