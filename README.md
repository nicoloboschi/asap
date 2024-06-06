# ASAP, speed up local Maven builds 🚀 

## Why
When working locally with Maven based applications, you might find yourself in running usual commands such as `mvn clean install -pl <mypackage> -DskipTests`. 
Most of the projects have useful-yet-annoying plugins such as checkstyle, spotbugs, javadoc, spotless and son an, that slows down your build - and they are really unecessary while you just want to try your code!

`asap` CLI helps you skipping all these plugins without wring 120-character-long command every time in different projects.

It works in 2 ways:
1. Prepend `asap` to `mvn` commands. All the plugins will be skipped automatically.
2. Use `asap` builtin commands to get things compiled fast.


## Installation

```
curl -Ls "https://raw.githubusercontent.com/nicoloboschi/asap/main/get-asap.sh" | bash
```

## Get started 

### Prepending `asap`

```
asap mvn package
```
will be transformed in
```
mvn package -Dcheckstyle.skip ....
```

### Using builtin commands

`asap` assumes you are using `mvn` but by default try to use [`mvnd`](https://github.com/apache/maven-mvnd) to increase the build speed.

- `asap mod <module>`: build the module (`install`) with dependant modules (`-am`)
- `asap cmod <module>`: build and clean the module (`install`) with dependant modules (`-am`)
- `asap modonly <module>`: build the module (`install`) without dependant modules
- `asap cmodonly <module>`: build and clean the module (`install`) without dependant modules
- `asap test <module> <test-class/method>`: run tests for a module, you can specify a class/method
- `asap dep <module>`: show dependencies of a module. You can append `-Dscope=compile` to remove test dependencies.

To build the current directory module, just pass `.` as `module`.

## Reference

This is the complete list of flags and plugins handled by `asap`. 

### Flags
- `-nsu`

### Plugins
- [maven-checkstyle-plugin](https://maven.apache.org/plugins/maven-checkstyle-plugin/index.html)
- [maven-spotbugs-plugin](https://spotbugs.readthedocs.io/en/stable/maven.html)
- [maven-javadoc-plugin](https://maven.apache.org/plugins/maven-javadoc-plugin/)
- [apache-rat-plugin](https://creadur.apache.org/rat/apache-rat-plugin/)
- [license-maven-plugin](https://www.mojohaus.org/license-maven-plugin/)
- [spotless-maven-plugin](https://github.com/diffplug/spotless/tree/main/plugin-maven)


