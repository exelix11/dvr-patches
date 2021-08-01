# dvr-patches

This is a set of exefs patches to allow streaming most switch games with [sysdvr](https://github.com/exelix11/SysDVR)

This is experimental and I did not test it with many games, **use at your own risk: may not work at all, cause instability and crashes or degrade performances.**

I doubt this can get you banned but again, **use at your own risk**.

## Firmware compatibility
**The provided patches are only for 12.1, 11.0 and 11.0.1** as they are the only firmwares I could test. If these prove not to cause issues I will port them to older versions as well. Of course pull requests are welcome.

## Installing
Download this repo as a zip file from the green "code" button on the top of the page [or this link](http://github.com/exelix11/dvr-patches/archive/master.zip), extract it and copy the `am` folder to `/atmosphere/exefs_patches/` on your sd then reboot your console. Now streaming should just work™.

## Game compatibility
I don't know. 

If you find a game that doesn't work or crashes with this open an issue. If you get a crash with title id `0100000000000023` it's most likely because of this.

## Technical stuff
### What do these patches do ?
Currently only the AM sysmodule is patched, the following changes are made:
- Am will always behave as if a game has auto recording enabled in its nacp
- The function to block recording in certain sections of the game is stubbed 
- As a nice bonus, the function games use to load an overlay image is stubbed

### Didn't you say this wouldn't work without patching games ?
I did. Turns out I probably made a mistake during my initial testing while in fact most games seem to work just fine without patching. \
That said, some games may have memory issues and require additional patches, in that case i'm fine with hosting them here if anyone is willing to PR them (.ips format only)
