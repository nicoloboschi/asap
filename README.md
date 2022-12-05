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
