[Back to Table of Contents](../Notes.md)
***
## Additional Points to Know

* MLO can be stored in two ways:
1. In FAT File system as Image File named "MLO".
2. In RAW mode where the Image starts from the 0th address of the Storage device.
<br/>
Refer the below document for more details.
![Modes of Storage of MLO](../Images/ModesOfMLOStorage.png)

* Storage can be partitioned into either of the below ways for booting:
1.

| Partition | Files | Format |
|:---------:|:-----:|:------:|
|     1     | MLO + U-Boot + uEnv.txt + uImage | FAT |
|     2     | RFS   | EXT3/EXT4 |

-- OR --

2. 
![Boot Partition Method 2](../Images/BootPartitionMethod2.png)


***

[Back to Table of Contents](../Notes.md)

