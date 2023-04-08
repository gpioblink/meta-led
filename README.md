# WIP: meta-led

This layer enable led function for "meta-licheepinano".

## how to use

In your build directory, add following line to the bottom of "bblayers.conf" file.

Line `/opt/nanowork/yocto/poky/meta-led` added.

```
BBLAYERS ?= " \
  /opt/nanowork/yocto/poky/meta-licheepinano \
  /opt/nanowork/yocto/build/licheepinano/workspace \
  /opt/nanowork/yocto/poky/meta-led \
  "
```

Then, in your poky directory, add machine config for "meta-licheepinano/conf/machine/licheepinano-sdcard.conf".

Change line `MACHINE_ESSENTIAL_EXTRA_RRECOMMENDS = " kernel-modules"` to `MACHINE_ESSENTIAL_EXTRA_RRECOMMENDS = " kernel-modules kernel-module-hello"`

```

MACHINE_ESSENTIAL_EXTRA_RRECOMMENDS = " kernel-modules kernel-module-hello"
MACHINE_ESSENTIAL_EXTRA_RDEPENDS = "kernel-image kernel-devicetree"

```

After that, just execute "bitbake core-image-minimal". If you burn the generated image to the sdcard, you can see "hello" kernel module.


