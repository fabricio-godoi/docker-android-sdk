# Docker Android SDK

This is a Docker project to compile any Android project with Gradle support. 
The container uses the alpine version, to be lightweight, which should be enough for most projects. It gets the Android SDK release from Android official repository (current version 26.1.1).

*NOTE* that by using this tool, your are automatically agreeing with the Android SDK terms of use. Use at your own risk. Check [Android Developer Website](https://developer.android.com/studio/) for more information.


## How to use

Clone the project or just download the [Dockerfile](https://github.com/fabricio-godoi/docker-android-sdk/blob/master/Dockerfile) in any directory of your choice, eg. [DIRECTORY].


* Generate the image with:

```
cd [DIRECTORY]
docker build -t android-sdk .
```

* Go to the root of the Android project and run the compiler with:

```
docker run --rm -v "$PWD":/project -w /project android-sdk chmod +X ./gradlew && ./gradlew assemble[Version]
```

Where "[Version]" is the release type of your Android project defined in the Gradle.

## License
[MIT License](https://github.com/fabricio-godoi/docker-android-sdk/blob/master/LICENSE)


