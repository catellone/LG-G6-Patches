# ___LG G6 Patches___
___Some patches for the LG G6___

To apply this patches, simply go to the main folder of your source (ex: "`cd lineage`") and copy & paste these patches.

`REMEMBER TO APPLY THIS PATCHES AFTER EVERY REPO SYNC BEFORE BUILD THE ROM.`

# CAM FIX
Our LG G6 need a patch to the **/framework/base** to properly switch through the lens
```
cd frameworks/base/ && git fetch https://github.com/LG-G6/android_frameworks_base.git lineage-18.1 && git cherry-pick 2bb23e9ca3adb657b64147e29c53fd7dac383bb6 e4af95d7a4da898ef0ac2e9085806cd0f8cbc0b2 && cd ../../
```
# SIGNATURE SPOOFING (MICROG SUPPORT)
```
cd frameworks/base/ && git fetch https://github.com/LG-G6/android_frameworks_base.git lineage-18.1 && git cherry-pick 826b9344ccb9d533f763360203f54f42d542aa01 && cd ../../
```
# TCP FIX
Our builds atm, need this patch to avoid TCP crashes, caused by netlink module. **NetworkStack** keep searching for that module, but isn't present in legacy kernel (version lower than 4.4)
```
cd packages/modules/NetworkStack/src/com/android/networkstack/netlink && git fetch https://github.com/catellone/packages_modules_NetworkStack.git android-R && git cherry-pick 56536b75d9e28857a78ff0defa36d452153132f6 && cd ../../../../../../../../
```
# WIFI DISPLAY FIX
```
cd frameworks/av && git fetch https://github.com/LineageOS/android_frameworks_av.git && git cherry-pick 9904747886e7f806e2b798af40b3021aac6d3916 562c08b4ef6a67ac67f249e7a95cd3018615df89 7746d18b79ec987313e20e7bc441d05659838cc0 930e597e0a5d1d4f4d9d92c5c6ca229167579bcc 535fd9b2c6d0b85ea850c8f43c8bdb8a1bcc1594 11799cffd9e4c068dd24bd1371c4f12f63de98e6 9009eefddc99692e691697ea9e75f7768234e053 d6357492605501092ebf0c13082088fa4b5f1ac8 && cd ../../
```
