# android_device_xiaomi_cepheus
Modded device tree for MI 9

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/cepheus" name="woacepherus/android_device_xiaomi_cepheus" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_cepheus-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/cepheus/recovery.img
```

## Other Sources

https://github.com/LasagnaTeam/TWRP_Kernel_Cepheus

## Thanks

- Thanks to @bibarub for helping editing scripts from vayu TWRP mod
