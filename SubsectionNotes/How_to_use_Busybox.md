[Back to Table of Contents](../Notes.md)
***

Download the latest [Busybox source code](https://busybox.net/downloads/)

# How to use Busybox to create a Minimal RFS?

1. Navigate inside the source code Directory and type the below command to apply default configuration 

```
make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- defconfig 
```

2. We may directly start compiling, but we may want to change the default settings for our product. 

```
make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- menuconfig 
```

3. After changing the settings, we are ready to compile the RFS.

```
make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- CONFIG_PREFIX=<installation path> install
```

***

[Back to Table of Contents](../Notes.md)

