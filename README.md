# ASAP, speed up your local builds

Speed up your local builds.
Prepend 'asap' to maven commands to get useless checks to be skipped while you're developing locally.

Only maven is supported. (`mvnd` as well ;) )

## Get started

```
curl -Ls "https://raw.githubusercontent.com/nicoloboschi/asap/main/get-asap.sh" | bash
```

```
asap mvn package
```

## Additional flags
- `-nsu`

## Skipped plugins
- Spotbugs
- Checkstyle
- Javadoc
- Apache RAT
- License checks


## Builtin commands
ASAP provides you builtin commands for daily activities.
All of the following commands assume you're using Maven.
You can append any other flag after the command.


- `asap mod <module>`: build the module (`install`) with dependant modules (`-am`)
- `asap cmod <module>`: build and clean the module (`install`) with dependant modules (`-am`)
- `asap modonly <module>`: build the module (`install`) without dependant modules
- `asap cmodonly <module>`: build and clean the module (`install`) without dependant modules
- `asap test <module> <test-class/method>`: run tests for a module, you can specify a class/method
- `asap dep <module>`: show dependencies of a module. You can append `-Dscope=compile` to remove test dependencies.


To build the current directory module, just pass `.` as `module`.