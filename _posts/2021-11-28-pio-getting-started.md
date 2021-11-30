---
layout: post
title:  "Getting Started With Platform IO"
date:   2021-11-28 12:38:50 +0200
categories: blog embedded
usemathjax: true
---

# Getting Started With Platform IO

>[Platform IO](https://platformio.org) is a command line tool as well as a Visual Studio Code extension useful for embedded development.

## Installation

1. Install [Visual Studio Code](https://code.visualstudio.com) (free, open source text editor)
2. Inside VSCode, click the extensions button and search for `“Platform IO”`
3. Click `Install`
4. The extension will ask you to reload your editor. Click reload (or close and reopen)
5. (optional) Install C/C++ extension (useful for code linting)


![](/assets/img/pio-ext.png)



## Toolchain Setup and Example Project

### Install Platform

1. Click on the Platform IO button on the left bar and click `PIO Home` -> `Open`
2. Click on `Platforms` on the left PIO bar
3. If it says no results found, you are in the `“Installed”` tab. Click on `“Install embedded platform”`
4. Search for your platform there, for example `nRF52`
5. Find the correct entry, select it and click `Install`

![](/assets/img/pio-open.png)

![](/assets/img/platform.png)

### Install Toolchain

1. Click on `Home` in the left PIO bar
2. Click `Project Examples`
3. Select an appropriate example for your platform (eg `nRF52`) using your preferred framework (eg `mbed`)

![](/assets/img/platform-install.png)

![](/assets/img/examples.png)

### Configure Project

In the file `platformio.ini` you can find the settings for building and uploading your project. You can find all the available configuration options in the [official documentation](https://docs.platformio.org/en/latest/projectconf/index.html).

You might need to change a few of the options according to your specific board and framework:

1. In the PlatformIO website, find your board on [this page](https://docs.platformio.org/en/latest/boards/index.html).
2. In the `Configuration` section, you can see the exact platformio.ini config you need to have
3. In the `Uploading` section you can find a list of available upload protocols that are supported for your board. The default is probably fine
4. In the `Debugging` section, you can see a the supported options for hardware debugging
5. In the `Frameworks` section, you can see the available frameworks that are supported

## Building and Uploading Binaries

The bottom bar has a few shortcuts for performing some basic operations. Hover your mouse over each icon to see what it does.

![](/assets/img/bottom-bar.png)

You can build your project using the check button, and upload it to your board using the right arrow button. The wall plug button opens a serial terminal so you can communicate with your board over the Serial interface.

## Troubleshooting

If the uploader does not find your board, or if you have multiple devices, click on Devices on the left PIO bar. If you can see your device there, copy the port it is connected to and set ```upload_port = <your_port>``` in the file `platformio.ini`.

All of the boards and upload protocols I’ve tested work out of the box on Linux. If you are using Windows, some drivers might not be installed by default. The easiest way to install those drivers is to use the [Zadig tool](https://zadig.akeo.ie).
