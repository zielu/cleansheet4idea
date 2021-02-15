Clean Sheet Theme for Jetbrains IDEs
======================================
Port of Eclipse [Clean Sheet theme](https://fappel.github.io/xiliary/clean-sheet.html)

## Features
For list of features see [description](./cleansheet/description.html)

## Change notes
For list of change notes see [changenotes](./cleansheet/change-notes.html)

## XML starlet
Removed options with name that starts with `VALUE.`
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
gradle clean buildPlugin release
```
#### Upgrade to next minor version
```
gradle clean buildPlugin releaseMinorVersion
```
#### Upgrade to next major version
```
gradle clean buildPlugin releaseMajorVersion
```

### Useful build commands
Update gradlew version
```
gradle wrapper --gradle-version 4.7 --distribution-type ALL
```

#### Release and publish
Append ```-Ppublish=true``` and include ```publishPlugin``` task.
For example
```
gradle clean check buildPlugin release publishPlugin -Ppublish=true
```

### Useful run commands
Run with previous sandbox contents
```
gradle runIde
```
Run with fresh sandbox
```
gradle clean runIde
```
