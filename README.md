# Android NDK Gradle
[![/android-ndk-gradle](http://dockeri.co/image/alexisduque/android-ndk-gradle)](https://hub.docker.com/r/alexisduque/android-ndk-gradle/)

## Included
* OpenJDK 8
* Git
* Gradle 2.14.1
* Android NDK r13b
* Android SDK (android-24,android-25)
* Android Build-tools (24.0.0,24.0.1,24.0.2,24.0.3,25.0.2)
* Android System Images(sys-img-armeabi-v7a-android-24,sys-img-armeabi-v7a-android-25)
* Android Support Libraries
* Google Play Services

## Build image

```bash
docker build -t alexisduque/android-ndk-gradle .
```

## Push build version to repository

```bash
docker push alexisduque/android-ndk-gradle
```

## Usage

### GitLab CI

This is what my .gitlab-ci.yml looks like:

```yaml
image: alexisduque/android-ndk-gradle
stages:
  - build

build:
  stage: build
  script:
    - gradle build
  only:
    - master

```

### Without GitLab

```bash
docker pull alexisduque/android-ndk-gradle
```

Change directory to your project directory, then run:

```bash
docker run --tty --interactive --volume=$(pwd):/opt/workspace --workdir=/opt/workspace --rm alexisduque/android-gradle  /bin/sh -c "gradle build"
```
