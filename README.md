# LoRaWAN Test App for Apache NuttX OS

Read the articles...

-   ["LoRa SX1262 on Apache NuttX OS"](https://lupyuen.github.io/articles/sx1262)

-   ["SPI on Apache NuttX OS"](https://lupyuen.github.io/articles/spi2)

This repo depends on...

-   [lupyuen/LoRaMac-node-nuttx](https://github.com/lupyuen/LoRaMac-node-nuttx)

To add this repo to your NuttX project...

```bash
cd nuttx/apps/examples
git submodule add https://github.com/lupyuen/lorawan_test
```

Then update the NuttX Build Config...

```bash
## TODO: Change this to the path of our "incubator-nuttx" folder
cd nuttx/nuttx

## Preserve the Build Config
cp .config ../config

## Erase the Build Config and Kconfig files
make distclean

## For BL602: Configure the build for BL602
./tools/configure.sh bl602evb:nsh

## For ESP32: Configure the build for ESP32.
## TODO: Change "esp32-devkitc" to our ESP32 board.
./tools/configure.sh esp32-devkitc:nsh

## Restore the Build Config
cp ../config .config

## Edit the Build Config
make menuconfig 
```

In menuconfig, enable the LoRaWAN Test App under "Application Configuration" → "Examples".

Based on...

-   [LoRaMac/fuota-test-01](https://github.com/lupyuen/LoRaMac-node-nuttx/blob/master/src/apps/LoRaMac/fuota-test-01/B-L072Z-LRWAN1)

-   [LoRaMac/periodic-uplink-lpp](https://github.com/lupyuen/LoRaMac-node-nuttx/blob/master/src/apps/LoRaMac/periodic-uplink-lpp/B-L072Z-LRWAN1)
