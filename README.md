# The Ploopy Mouse

By some stroke of luck, you've made your way here. The Ploopy Mouse. Your life will never be the same.

If you're looking to get your hands on a QMK-powered mouse, [check out our store link](https://ploopy.co/shop/mouse/)!

This repository contains the schematic for the Ploopy Mouse. If you're looking for the firmware that gets shipped with every mouse, check out the [QMK repository](https://github.com/qmk/qmk_firmware).

As of this writing, we are currently shipping every Ploopy Mouse with [QMK Release Version 0.10.48](https://github.com/qmk/qmk_firmware/releases/tag/0.10.48), which we've vetted and guarantee to be stable. If you want, however, you can flash the latest version of QMK onto your device. Although we cannot guarantee that the build will be stable, the developers at QMK do an excellent job ensuring that stable, tested code is in the QMK repository.

What are you waiting for? Your new life awaits.

## QMK Firmware

If you're looking for a hex file containing working QMK code with a keymapping compatible with VIA, it's available here. The hex was built with QMK version 0.11.1.

## Under what license is this released?

Everything in this repository is released under OHL CERN v1.2. Check the LICENSE.md file for full license text.

# How to Flash New Firmware

The Ploopy Mouse is fairly easy to program and reprogram, thanks to the excellent work by all of the developers and maintainers of the [QMK firmware suite](https://github.com/qmk/qmk_firmware). This guide will focus specifically on flashing firmware to the Ploopy Mouse.

## Before you begin

If you have never used QMK before, go through [all of the steps in the QMK guide to set up your environment](https://docs.qmk.fm/#/newbs_getting_started).

QMK was built for keyboards, so you'll see lots of references to code that looks like the following:

`-kb <keyboard>`

Whenever you see that, use the following syntax:

`-kb ploopyco/mouse`

and you'll be fine.

## Building the Ploopy Mouse firmware

With your terminal window open and pointed at your QMK build environment, compile the firmware with the following command:

`qmk compile -kb ploopyco/mouse -km via`

Alternatively, you can invoke the Makefile directly with the following:

`make ploopyco/mouse:via`

If you wish, you can use the default keymap (with `qmk compile -kb ploopyco/mouse -km default` or `make ploopyco/mouse:default`). However, the VIA keymap is particularly interesting because it allows for customization of the mouse's functions without reflashing the firmware, through the use of the convenient [VIA software package](https://github.com/the-via/releases/releases). It's incredibly handy, so definitely check it out.

For more details on building QMK firmware in general, see the [QMK firmware guide](https://docs.qmk.fm/#/newbs_building_firmware).

## Putting the Ploopy Mouse into bootloader mode

Putting the Ploopy Mouse into bootloader mode is very easy.

1. Unplug it from your computer.
2. Hold the "back" button. This is the button on the side of the mouse that is closer to the bottom of your hand.
3. While holding the back button, plug the Ploopy Mouse into your computer. If you're using QMK Toolbox, it should show up in the console. If using `dmesg`, it'll show up as an Atmel DFU device.

And that's it. While plugged in this way, the Ploopy Mouse will accept new firmware.

## Flashing the firmware

Use your preferred method of flashing QMK firmware.

- QMK Toolbox has been verified as working.
- Using `dfu-programmer` from a terminal window has also been verified as working.

For more details, see the [QMK guide](https://docs.qmk.fm/#/newbs_flashing) on flashing firmware.

## And that's it!

Unplug it, replug it in, and you should be good to go!

Happy customizing!

## Acknowledgements

Very special thanks to [drashna](https://github.com/drashna). He wrote a ton of the code that makes this thing go. Check out some of his other projects!
