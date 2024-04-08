[Back to Table of Contents](../Notes.md)
***
## Booting Beaglebone Black Board from the SD card

* Prebuilt binaries of MLO, U-boot, Linux image from Angstrom Repository can be found at:
<br/>
[GitHub Page: Angstrom Demo](https://github.com/niekiran/EmbeddedLinuxBBB/tree/master/pre-built-images/Angstrom_Demo)

**Steps:**

1) Take an uSD card (4GB >= ) and partition it to two as shown below.
<br/>
(For more information about partitioning uSD card read: [How to Partition the uSD card for Booting](SubsectionNotes/How_to_Partition_uSD_card.md))

![uSD card Partitions](../Images/uSD_card_partitions.png)
<br/>
<br/>
2. Next, Copy the MLO file to the BOOT partition of the uSD card and Rename it as "MLO". You need root privilege to copy it, so use 'sudo' as said earlier. (Refer [Important Note](SubsectionNotes/How_to_Partition_uSD_card.md))
<br/>
```
sudo cp <path of the MLO file> /media/<username>/BOOT/MLO
```
<br/>
3. Then, Copy the U-boot file to the BOOT partition of the uSD card and Rename it as "u-boot.img". 
<br/>

```
sudo cp <path of the u-boot.img file> /media/<username>/BOOT/u-boot.img
```

<br/>

4. Later, Download the RFS (Root File system) from the provided source and extract it. Here if you go inside the boot folder find "uImage" file and this is the Linux Image. Now, come back and copy all the folders into the ROOTFS partition of the uSD card. And then run "sync".
<br/>

```
sudo cp -r <path of the RFS folder>/* /media/<username>/ROOTFS/
sync
```

<br/>

***

[Back to Table of Contents](../Notes.md)

Next: []()
<br/>
Previous: []()
