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

## Addiotional flags
- `-nsu`

## Skipped plugins
- Spotbugs
- Checkstyle
- Javadoc
- Apache RAT
- License checks


## Fast compile single module

```
asap mod <module_name>
```

is equivalent to 

```
mvn[d] install -am -DskipTests -pl <module_name> <skipped_plugins>
```

## Fast run test class/method

```
asap test <module_name> <class_or_method>
```

is equivalent to 

```
mvn[d] test  -pl <module_name> -Dtest=<class_or_method> <skipped_plugins>
```