# SDK Extension for OpenJDK 11

This extension contains the OpenJDK 11 Java Runtime Environment (JRE) and Java Developement Kit (JDK).

OpenJDK 11 is the previous long-term support (LTS) version.

For the current LTS version, see the [OpenJDK 17](https://github.com/flathub/org.freedesktop.Sdk.Extension.openjdk17) extension.

For the current latest (non-LTS) version, see the [OpenJDK](https://github.com/flathub/org.freedesktop.Sdk.Extension.openjdk) extension.

## Usage

You can bundle the JRE with your Flatpak application by adding this SDK extension to your Flatpak manifest and calling the install.sh script. For example:

```
{
  "id" : "org.example.MyApp",
  "branch" : "1.0",
  "runtime" : "org.freedesktop.Platform",
  "runtime-version" : "23.08",
  "sdk" : "org.freedesktop.Sdk",
  "sdk-extensions" : [ "org.freedesktop.Sdk.Extension.openjdk11" ],
  "modules" : [ {
    "name" : "openjdk",
    "buildsystem" : "simple",
    "build-commands" : [ "/usr/lib/sdk/openjdk11/install.sh" ]
  }, {
    "name" : "myapp",
    "buildsystem" : "simple",
    ....
  } ]
  ....
  "finish-args" : [ "--env=PATH=/app/jre/bin:/usr/bin" ]
}
```
