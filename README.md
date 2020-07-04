# Bote-Link-FW

Firmware for [Bote-Link](https://github.com/connorrigby/bote-link) USB/CAN
passthru device.

Very much a work in progress. If for some reason you stumble upon this and want
information or help, [join my Discord](https://discord.gg/epHw2DE) and check
out the [trello board](https://trello.com/b/Xmjmzd9U/botelink-project-board)


## Planned Features

* ECU Firmware Dump/Flash
* SDCard Logging
* UDS Mode 0x23 logging to SDCard
* USB virtual COM port for use with TunerStudio and [Speediview](https://github.com/ConnorRigby/speediview)
* Integration with [RomDrop](https://github.com/speepsio/romdrop)

## Building

First, install a compatible toolchain.
[ARM publishes one](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm)

```bash
git clone git@github.com:connorrigby/bote-link-fw.git
cd bote-link-fw/
git submodule update --init --recursive
make
```

## Notes

* [stm32f1xx CAN example](https://github.com/STMicroelectronics/STM32CubeF1/blob/441b2cbdc25aa50437a59c4bffe22b88e78942c9/Projects/STM3210E_EVAL/Examples/CAN/CAN_Networking/Src/main.c)

```c
// memory location: 0xFFFFAC08
typedef struct
{
    unsigned char ethanolContent;
    unsigned char fuelTemp;
    unsigned char timeout;
    unsigned char errorStatus;
} flexFuelSensor;
```
