# dvr-patches
[![Discord](https://img.shields.io/discord/643436008452521984.svg?logo=discord&logoColor=white&label=Discord&color=7289DA
)](https://discord.gg/rqU5Tf8)
[![Latest release](https://img.shields.io/github/v/release/exelix11/dvr-patches)](https://github.com/exelix11/dvr-patches/releases)
[![Downloads](https://img.shields.io/github/downloads/exelix11/dvr-patches/total)](https://github.com/exelix11/dvr-patches/releases)
[![ko-fi](https://img.shields.io/badge/supporting-ko--fi-f96854)](https://ko-fi.com/exelix11)

This is a set of exefs patches to allow streaming incompatible games with [sysdvr](https://github.com/exelix11/SysDVR)

This is experimental and I did not test it with many games, **use at your own risk: may not work at all, cause instability and crashes or degrade performances.**

I doubt this can get you banned but again, **use at your own risk**.

## Firmware compatibility
**Only the following firmwares are supported: 13.1, 13.0, 12.1, 11.0 and 11.0.1**. I have no plans to port to older firmwares, of course pull requests are welcome.

## Installing
Download `dvr-patches.zip` from latest [release](https://github.com/exelix11/dvr-patches/releases) and extract it to the root of your sd card then reboot your console. Now streaming should just work™.

Every time you install a new firmware update you'll probably need to download a new version of these patches which may not be available right away, check the commit messages to know when support for a new firmware is added.

## Game compatibility
Most games seem to work fine, a few have been reported to not work or crash, check out the [issues](https://github.com/exelix11/dvr-patches/issues) tab for a list.

If you find a game that doesn't work or crashes with this open an issue, although i can't guarantee i'll be able to fix it.\
If you get a crash with title id `0100000000000023` it's most likely because of this.

## Technical stuff
### What do these patches do ?
Currently only the AM sysmodule is patched, the following changes are made:
- All games that don't support recording will behave as if they have auto recording enabled in the nacp.
- All games will have screenshots enabled in the nacp.
- Am's code flow is adjusted to avoid crashing when memory allocation for auto recording fails.
- The function to block recording in certain sections of the game is stubbed .
- As a nice bonus, the function games use to load an overlay image is stubbed.

If you want to port these patches to different firmware versions, check out [porting notes](https://github.com/exelix11/dvr-patches/wiki/Porting-notes)

### Didn't you say this wouldn't work without patching games ?
I did. Turns out I probably made a mistake during my initial testing while in fact most games seem to work just fine without patching. \
That said, some games may have memory issues and require additional patches, in that case i'm fine with hosting them here if anyone is willing to PR them (.ips format only)
