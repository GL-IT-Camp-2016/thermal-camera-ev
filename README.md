# `thermal-camera`

Upgraded firmware for ESP32 based thermal camera originaly designed by [themainframe](damow.net).
Original firmware can be found [here](https://github.com/themainframe/thermal-camera).

Toolchain used and the way of building are the same as in the original.

## Changes against the original
In addition to Fusion palette, 4 new palettes are now avaiable: Super fusion, White hot, Black hot and Rainbow, as well as a way to switch between them. You can change palette by pressing a button connected to a pin number 26.

Simple low battery check is also implemented. Single-cell Li-Ion battery is connected to pin number 34 by 50/50 voltage divider (important as Li-Ion battery has higher voltage than ESP32 is operating at).

## Building

To build, check out this repository first.

Install the appropriate ESP32 Extensa toolchain for your system - see [https://esp-idf.readthedocs.io/en/v3.0-rc1/get-started/index.html](https://esp-idf.readthedocs.io/en/v3.0-rc1/get-started/index.html). Make sure you're looking at the v3.0-rc1 version documentation, otherwise the wrong toolchain links will be provided. It's critical that the compilation is performed with the correct toolchain.

Also check out the ESP32 IoT Development Framework (IDF):

    git clone https://github.com/espressif/esp-idf.git esp-idf
    cd esp-idf
    git checkout v3.0-rc1
    git submodule update --init --recursive

Set the `IDF_PATH` environment variable to point to the path where you checked out the IDF above.

In the `thermal-camera` directory, set up your serial port settings with `make menuconfig`.

Build with `make`.

Flash with `make flash`.

