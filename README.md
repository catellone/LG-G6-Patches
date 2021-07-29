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
