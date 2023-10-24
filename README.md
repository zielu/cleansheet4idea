Clean Sheet Theme for Jetbrains IDEs
======================================
Port of Eclipse [Clean Sheet theme](https://fappel.github.io/xiliary/clean-sheet.html)

![Preview](preview.png?raw=true "Preview")

## Features
For list of features see [description](./cleansheet/description.html)

## Change notes
For list of change notes see [changenotes](./cleansheet/change-notes.html)

## XML starlet
Removed options with `@name` that starts with `VALUE.`
```
xml ed -d "/scheme/attributes/option[starts-with(@name, 'VALUE.')]" cleansheet.xml
```

## Building & running

### Build parameters
```-Pfast=true``` speed-up is achieved by:
* skipping integration tests 
* skipping spotbugs

### Releases

#### Release current `-SNAPSHOT`
```
./gradlew clean buildPlugin release
```
#### Upgrade to next minor version
```
./gradlew clean buildPlugin releaseMinorVersion
```
#### Upgrade to next major version
```
./gradlew clean buildPlugin releaseMajorVersion
```

### Useful build commands
Update gradlew version
```
./gradlew wrapper --gradle-version 8.4 --distribution-type ALL
```

#### Release and publish
Append ```-Ppublish=true``` and include ```publishPlugin``` task.
For example
```
./gradlew clean check buildPlugin release publishPlugin -Ppublish=true
```

### Useful run commands
Run with previous sandbox contents
```
./gradlew runIde
```
Run with fresh sandbox
```
./gradlew clean runIde
```
