<h1 align="center">Golden Launcher</h1>

<img src="https://raw.githubusercontent.com/Golden-Launcher/Golden-Launcher/refs/heads/v3_openjdk/app_pojavlauncher/src/main/assets/amethyst.png" align="left" width="130" height="130" alt="Golden Launcher Logo">

<p align="center">
  <img src="https://img.shields.io/github/commit-activity/m/Golden-Launcher/Golden-Launcher" alt="GitHub commit activity"/>
  <img src="https://img.shields.io/badge/platform-Android-green" alt="Platform"/>
  <img src="https://img.shields.io/badge/minSdk-26-blue" alt="Min SDK"/>
  <img src="https://github.com/Golden-Launcher/Golden-Launcher/workflows/Android%20CI/badge.svg" alt="Android CI"/>
  <img src="https://badges.crowdin.net/pojavlauncher/localized.svg" alt="Crowdin"/>
  <a href="https://discord.gg/nta5RctJQT"><img src="https://img.shields.io/discord/1355213558631366897?color=5865F2&logo=discord&logoColor=white&label=&style=flat" alt="Discord"></a>
  <a href="https://github.com/Golden-Launcher"><img src="https://img.shields.io/badge/github-GoldenLauncher-orange?logo=github" alt="GitHub"></a>
</p>

Golden is a fork of [Copper](https://github.com/CopperLauncher/Copper-Android) that allows you to play Minecraft: Java Edition on your Android devices.

## Table of Contents

* [Introduction](#introduction)
* [Getting Golden](#getting-golden)
* [Building](#building)
    * [Quick Build (Recommended)](#quick-build-recommended)
    * [Detailed Build](#detailed-build)
* [Current Status](#current-status)
* [Known Issues](#known-issues)
* [FAQ](#faq)
* [Contributing](#contributing)
* [Support](#support)
* [License](#license)
* [Credits & Dependencies](#credits--dependencies)
* [Roadmap](#roadmap)

## Introduction

* Golden Launcher is a Minecraft: Java Edition launcher for Android based on [Boardwalk](https://github.com/zhuowei/Boardwalk), [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher), [Amethyst Launcher](https://github.com/AngelAuraMC/Amethyst-Android), and [Copper Launcher](https://github.com/CopperLauncher/Copper-Android).
* This launcher can launch almost all available Minecraft versions ranging from rd-132211 to 26.x snapshots (including Combat Test versions)
* Modding via Forge and Fabric are also supported.
* This repository contains source code for Android.

## Getting Golden

You can get Golden Launcher via three methods:

1. **Nightly** Download the latest artifact from [Nightly.link](https://nightly.link/Golden-Launcher/Golden-Launcher/workflows/android/v3_openjdk?preview)
2. **Releases:** Download the latest prebuilt app [from Releases](https://github.com/Golden-Launcher/Golden-Launcher/releases/)
3. **Build from Source:** Follow the [building instructions](#building) below.

## Building

### Quick Build (Recommended)

The easiest way to build Golden Launcher is to use the pre-built JREs provided by our CI.

1. Clone the repository: `git clone --recursive https://github.com/Golden-Launcher/Golden-Launcher.git`
2. Build the launcher: `./gradlew :app_pojavlauncher:assembleDebug` (Use `gradlew.bat` on Windows)

The built APK will be located in `app_pojavlauncher/build/outputs/apk/debug/`.

### Detailed Build

If you need more control over the build process, follow these steps:

1. **Java Runtime Environment (JRE):** Download the `jre8-pojav` artifact from AngelAuraMCs  [CI auto builds](https://github.com/AngelAuraMC/openjdk-build-multiarch/actions).  This package contains pre-built JREs for all supported architectures.  If you need to build the JRE yourself, follow the instructions in the [android-openjdk-build-multiarch](https://github.com/AngelAuraMC/openjdk-build-multiarch) repository.

2. **LWJGL:** The build instructions for the custom LWJGL are available over the [LWJGL repository](https://github.com/AngelAuraMC/lwjgl3).

3. **Language List:** Because languages are auto-added by Crowdin, you need to run the language list generator before building. In the project directory, run:
   * Linux/macOS:
     ```bash
     chmod +x scripts/languagelist_updater.sh
     bash scripts/languagelist_updater.sh
     ```
   * Windows:
     ```batch
     scripts\languagelist_updater.bat
     ```

4. **Build GLFW stub:** `./gradlew :jre_lwjgl3glfw:build`

5. **Build the launcher:** `./gradlew :app_pojavlauncher:assembleDebug` (Replace `gradlew` with `gradlew.bat` on Windows).

## Current Status

* [x] New UI
* [x] Bug Fixes
* [x] Fix GL4ES and KW in older versions
* [x] Add Modpack export
* [x] Add mclo.gs 
* [ ] Add More Renders


## Known Issues

See Golden Launcher's [issue tracker](https://github.com/Golden-Launcher/Golden-Launcher/issues) for a list of known issues and their current status.

## Support

For support, please join our [Discord server](https://discord.gg/nta5RctJQT)

## License

Golden Launcher is licensed under [GNU LGPLv3](https://github.com/Golden-Launcher/Golden-Launcher/blob/v3_openjdk/LICENSE).

## Credits & Dependencies

* [Boardwalk](https://github.com/zhuowei/Boardwalk) (JVM Launcher): Unknown License/[Apache License 2.0](https://github.com/zhuowei/Boardwalk/blob/master/LICENSE) or GNU GPLv2.
* [PojavLauncher](https://github.com/PojavLauncherTeam/PojavLauncher): [GLGPL](https://github.com/PojavLauncherTeam/PojavLauncher/blob/v3_openjdk/LICENSE)
* [Amethyst Launcher](https://github.com/AngelAuraMC/Amethyst-Android/): [LGPL-3.0 license](https://github.com/AngelAuraMC/Amethyst-Android/blob/v3_openjdk/LICENSE)
* [Copper Launcher](https://github.com/CopperLauncher/Copper-Android): [LGPL-3.0 license](https://github.com/CopperLauncher/Copper-Android/blob/v3_openjdk/LICENSE)
* [MojoLauncher](https://github.com/MojoLauncher/MojoLauncher/): [LGPL-3.0 license](https://github.com/AngelAuraMC/Amethyst-Android/blob/v3_openjdk/LICENSE)
* Android Support Libraries: [Apache License 2.0](https://android.googlesource.com/platform/prebuilts/maven_repo/android/+/master/NOTICE.txt).
* [GL4ES](https://github.com/AngelAuraMC/gl4es): [MIT License](https://github.com/ptitSeb/gl4es/blob/master/LICENSE).
* [MobileGlues](https://github.com/MobileGL-Dev/MobileGlues): [LGPL-2.1 License](https://github.com/MobileGL-Dev/MobileGlues/blob/dev-es/LICENSE).
* [ANGLE](https://chromium.googlesource.com/angle/angle): [All Rights Reserved](app_pojavlauncher/src/main/assets/licenses/ANGLE_LICENSE).
* [OpenJDK](https://github.com/AngelAuraMC/openjdk-multiarch-jdk8u): [GNU GPLv2 License](https://openjdk.java.net/legal/gplv2+ce.html).
* [LWJGL3](https://github.com/AngelAuraMC/lwjgl3): [BSD-3 License](https://github.com/LWJGL/lwjgl3/blob/master/LICENSE.md).
* [LWJGLX](https://github.com/AngelAuraMC/lwjglx) (LWJGL2 API compatibility layer for LWJGL3): unknown license.
* [Mesa 3D Graphics Library](https://gitlab.freedesktop.org/mesa/mesa): [MIT License](https://docs.mesa3d.org/license.html).
* [pro-grade](https://github.com/pro-grade/pro-grade) (Java sandboxing security manager): [Apache License 2.0](https://github.com/pro-grade/pro-grade/blob/master/LICENSE.txt).
* [bhook](https://github.com/bytedance/bhook) (Used for exit code trapping): [MIT license](https://github.com/bytedance/bhook/blob/main/LICENSE).
* [libepoxy](https://github.com/anholt/libepoxy): [MIT License](https://github.com/anholt/libepoxy/blob/master/COPYING).
* [virglrenderer](https://github.com/AngelAuraMC/virglrenderer): [MIT License](https://gitlab.freedesktop.org/virgl/virglrenderer/-/blob/master/COPYING).
* [OpenAL-Soft](https://github.com/kcat/openal-soft): [GNU GPLv2](app_pojavlauncher/src/main/assets/licenses/OPENAL-SOFT_GPL2)
  * [oboe](https://github.com/google/oboe): [Apache License 2.0](app_pojavlauncher/src/main/assets/licenses/OBOE_APACHE2).
  * [pfffft](https://bitbucket.org/jpommier/pffft/src/master/): [ARR](app_pojavlauncher/src/main/assets/licenses/PFFFT_LICENSE)
* [SDL3](https://github.com/libsdl-org/SDL): [zlib License](https://github.com/libsdl-org/SDL/blob/main/LICENSE.txt)
* [sdl2-compat](https://github.com/libsdl-org/sdl2-compat): [zlib License](https://github.com/libsdl-org/sdl2-compat/blob/main/LICENSE.txt)
* Thanks to [MCHeads](https://mc-heads.net) for providing Minecraft avatars.
* Thanks to [Modrinth](https://api.modrinth.com/), [CurseForge](https://docs.curseforge.com/rest-api/) and [McLo.gs](https://api.mclo.gs) for providing us the free API's.
* Special thanks to **maxjubayeryt** for the original Golden Launcher design aesthetic that inspired this project.

## Roadmap

We are currently focusing on:

* Exploring new rendering technologies.

Future plans include:

* Improving stability and performance.
* Enhancing the mod installation experience.

We welcome community feedback and suggestions for our roadmap.  Please feel free to open a feature request in our [issue tracker](https://github.com/Golden-Launcher/Golden-Launcher/issues).
