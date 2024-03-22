# meta-matter-raspberrypi
Build matter SDK Tools for Raspberry pi

# Things to do with what?
Yocto recipies to build chip-tool and other Matter SDK related tools on Raspberry pi 4 using NXP's mater SDK.
Use the source at the URL below.
https://github.com/NXP/matter

# Dependence
matter SDk build requires gn. Therefore, you need to add meta-qt6.

# Usage
## Get source from repositry.
```
cd poky
git clone https://github.com/kobayutapon/meta-matter-raspberrypi.git
```

## Add layer
```
bitbake-layers add-layer ../meta-matter-raspberrypi
bitbake-layers add-layer ../meta-qt6
```

Verify that the following line has been added to bblayer.conf

```
  /build/poky/meta-matter-raspberrypi \
  /build/poky/meta-qt6 \
```
## Fix local.conf
Add following line.
```
IMAGE_INSTALL:append = " matter"
```

## build
Run bitbake


# Notes
matter tools( like chip-tool, etc.. ) needs Wi-Fi and Bluetooth environment.
Remember to add these features.


