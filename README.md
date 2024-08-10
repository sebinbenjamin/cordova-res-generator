# image-res-generator
[![CircleCI build status](https://img.shields.io/circleci/build/github/sebinbenjamin/image-res-generator.svg)](https://circleci.com/gh/sebinbenjamin/image-res-generator)
[![Codeclimate Issues](https://img.shields.io/codeclimate/issues/sebinbenjamin/image-res-generator.svg)](https://codeclimate.com/github/sebinbenjamin/image-res-generator/issues)
[![Codeclimate Maintainability](https://img.shields.io/codeclimate/maintainability-percentage/sebinbenjamin/image-res-generator.svg)](https://codeclimate.com/github/sebinbenjamin/image-res-generator/maintainability)
[![Depfu](https://badges.depfu.com/badges/e26d90ff99e9d1681c0e0029b003cb9f/overview.svg)](https://depfu.com/github/sebinbenjamin/image-res-generator?project_id=8520)
[![Gitter Chat](https://img.shields.io/gitter/room/sebinbenjamin/image-res-generator.svg?color=blue)](https://gitter.im/image-res-generator/community)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## Introduction

Automatic icon and splash screen resizing tool. Helpful for quickly generating image assets for **Angular**/**Ionic**/**Capacitor**/**Cordova**/**PhoneGap** apps, PWAs, and general use.

It automatically resizes and copies your `icon.png` and `splash.png` files to the platform-dedicated directories.

---

## Installation

To install the `image-res-generator` globally, run:

```bash
npm install -g image-res-generator
```

This will make the `irgen` command available globally on your system.

### Verifying Installation

After installation, you can verify that the `irgen` command is available by running:

```bash
irgen --version
```

If the command is not recognized, make sure that the global npm binary path is included in your system's PATH environment variable.

---

## Usage

### Getting Started: A Step-by-Step Guide

1. **Install the Tool**:
    Make sure you've installed `image-res-generator` globally by running the command:

    ```bash
    npm install -g image-res-generator
    ```

2. **Prepare Your Images**:
    Place your `icon.png` and `splash.png` files in the `resources/` directory at the root of your project. These images should be at least (1024px x 1024px) for icons and (2732px x 2732px) for splash screens.

    **Example Directory Structure**:
    ```
    resources/
    ├── icon.png
    └── splash.png
    ```

    Alternatively, you can use `SVG` vector images:

    ```
    resources/
    ├── icon.svg
    └── splash.svg
    ```

3. **Generate Resized Images**:
    Open your terminal, navigate to the root directory of your project, and run the following command:

    ```bash
    irgen
    ```

    This command will resize and copy your images to the appropriate directories for each platform.

4. **Customize the Output**:
    If you want to customize the output or process only specific platforms, you can use the available options. For example, to generate resources only for Android and iOS, run:

    ```bash
    irgen -p android,ios
    ```

    Refer to the [Options](#options) section below for more details.

5. **Verify the Output**:
    After running the command, verify that the generated images are placed correctly in the platform-specific directories.

### Required Files

Add your `icon` and `splash` files to the 'resources' folder under the root of your project. Make sure they are at least (1024px x 1024px) for icons and (2732px x 2732px) for splash images. 

```
resources/
├── icon.png
└── splash.png
```

**Update**: You could now use `SVG` vector images for the same 🎉. 

```
resources/
├── icon.svg
└── splash.svg
```
While creating a base splash image, make sure that the splash screen's artwork roughly fits/covers a square (1200x1200) at the center of the image (2732x2732).

<img src="https://user-images.githubusercontent.com/4099066/82296073-bd052880-9a04-11ea-9ee7-199b6dc1e826.jpg" width="75%">

You can use this [template](https://code.ionicframework.com/resources/splash.psd) provided by the Ionic team for easier splash creation.

### Command Line

```bash
image-res-generator
```
or

```bash
irgen
```

**ATTENTION:** while preserving source files, it overwrites previous output if any.

### Options

```bash
-V, --version               output the version number
-i, --icon [optional]       optional icon file path
                            (default: ./resources/icon.png)
-s, --splash [optional]     optional splash file path
                            (default: ./resources/splash.png)
-p, --platforms [optional]  optional platform token comma separated list
                            available tokens: android, ios, windows, blackberry10, pwa
                            (default: all platforms processed)
-o, --outputdir [optional]  optional output directory
                            (default: ./resources/)
-I, --makeicon [optional]   option to process icon files only
-S, --makesplash [optional] option to process splash files only
-c, --crop[optional]        option to crop images, instead of the default 'resize' strategy. 
-h, --help                  output usage information
-d, --debug                 output debugging information
```

---

## Automating with NPM Scripts

Add to your package.json a script definition to match your file generation needs.
This way, you won't have to repeat the whole command along with the options.

### Example

```json
{
  "scripts": {
    "resgen": "irgen -p android,ios"
  }
}
```

### Usage

```bash
npm run resgen
```

NPM will handle typing the full command for you, reducing the chances of errors.

---

## Platforms Supported

Supported platforms:

- **iOS**
  - Icons
  - Splash Screens
- **Android**
  - Icons
  - Splash Screens
- **Windows**
  - Icons
  - Splash Screens
- **Blackberry 10**
  - Icons
- **PWAs**
  - Icons

---

## Upcoming Tasks
- Copy assets to Android/iOS Capacitor folders.
- Add options for crop resizing strategy.
- Update image configurations for all platforms.
- Add support for Capacitor.

---

## Contributing

Thanks for your interest in contributing! 
Read up on our [guidelines](https://github.com/sebinbenjamin/image-res-generator/blob/master/CONTRIBUTING.md) to start contributing.

If you encounter any issues or have suggestions, feel free to open an issue on our [GitHub repository](https://github.com/sebinbenjamin/image-res-generator/issues).

---

## Credits

This open-source project is made possible with the help and support of the amazing open-source community. Special thanks to:

- All contributors in this project ✨💚.
- [@olivab][1] for creating and maintaining the original project [cordova-res-generator][2].
- Contributors to [cordova-res-generator][2].

[1]: https://github.com/olivab
[2]: https://github.com/olivab/cordova-res-generator

---

## License

This project is made available under the terms of the GPLv3.
See the [LICENSE file][license] for the full text of the license.

[license]: https://github.com/sebinbenjamin/image-res-generator/blob/master/LICENSE
