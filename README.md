# TWRP device tree for Infinix Note 11 Pro (X697)

## Status

Specs [here](https://twrp.me/faq/OfficialMaintainer.html)

The tester [Simich07](https://4pda.to/forum/index.php?showuser=1671401) only install `boot-x697-A11-20220928-1932.img` test modified file to know if TWRP can start.

Some tests was made: Enc_Dec working. Removed one file with 1.36MB because not need and removing that, the Magisk can install with more free size.

Issue: unlocking screen not work - Hide TW_SCREEN_BLANK_ON_BOOT: Maybe this cause touch screen issue when unlocking screen.
Since Simich07 wrote about this issues with touch after unlocking screen off, he make a discover disabling the screen timeout. So in the flags we need write:
`TW_NO_SCREEN_TIMEOUT := true` and compiling other TWRP.img to new test.
```
# Try disabling the screen timeout. It is not a fix, but it can be an effective work-around.
TW_NO_SCREEN_TIMEOUT := true
```

New file with new version TWRP3.7.0: Need test after 2022-10-12

****2022-10-12****: Changes to made new version TWRP3.7.0

### This branch android-11 has ***encrypt/decrypt*** files and option to more test with that.

![TWRP Working](https://github.com/lopestom/twrp_device_infinix_x697/blob/android-11/picture/TWRP-IN_11_Pro-MT6871.png?raw=true)

-----
#### Building

```bash
source build/envsetup.sh
lunch twrp_x697-eng
mka bootimage
```

