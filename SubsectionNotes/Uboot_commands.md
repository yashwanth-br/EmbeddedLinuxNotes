[Back to Table of Contents](../Notes.md)
***

# U-Boot Most Useful commands and Syntax

1. __help__ - For getting all commands list.
2. __<command\> help__ - help for a particular command which we are interested in. (Replace <command\> with the desired command).
3. __load__ - To load from certain storage device on the board to the External RAM of the board.

    * Syntax - 

    `load <interface type> <device number>:<partition number> <RAM load address> <File name to be loaded>`
    * Example - 
    `load mmc 0:2 0x82000000 /boot/uImage`
    (This loads from MMC device 0 [i.e. from uSD card] partition 2 file named "_uImage_" to RAM address _0x82000000_)
4. __ext2ls__ - to list the files and folders present on a storage device.

    * Syntax - 

    `ext2ls <interface type> <device number>:<partition number>`
    * Example - 
    `ext2ls mmc 0:2`
    (This lists all the files and folders from uSD card partition 2)

5. __part list__ - to list all the partition on a storage device.

    * Syntax - 

    `part list <interface type> <device number>`    

    * Example - 
    `part list mmc 0`
    (This lists all the partitions of the storage)
6. __boot__ - Start to boot from reading uEnv.txt, if uEnv.txt is not present it will start to boot with default values.
7. __bootm__ - Start to boot from the RAM starting from the given kernel image address. Here <initramfs\> <flattened device tree binary\> is optional.

    * Syntax - 

    `bootm <kernel image address> <initramfs> <flattened device tree binary>`
    * Example 1 - 
    `bootm 0x82000000`
    (Boot from 0x82000000)
    * Example 2 - 
    `bootm 0x82000000 0x88080000 0x88000000`
    (Boot from 0x82000000 with initramfs at 0x88080000 and dtb at 0x88000000)
    * Example 3 - 
    `bootm 0x82000000 - 0x88000000`
    (Boot from 0x82000000 with dtb at 0x88000000)
8. __printenv__ - to list all the environmental variables and its values.

9. __printenv <environmental variable\>__ - to print the value of an environmental variable.

10. __run <command\>__ - to run the command/environmental variable.

11. __setenv__ - to assign a value to certain environmental variable/create variable if not present.

    * Syntax - 

    `setenv <variable name> <value>`    

    * Example - 
    `setenv serverip 192.168.7.1`
    (Set the value of serverip as 192.168.7.1)

12. __mmc rescan__ - to rescan for any mmc device added after the u-boot booting.

13. __mmc list__ - to list all the available mmc interface on the board.

### Points to Note:

1. You can store multiple commands in the environmental variables and later execute all of them on one go by running this one environmental variable.
    * Example - 

    `setenv com1 load mmc 0:2 0x82000000 /boot/uImage; load mmc 0:2 0x88000000 /boot/deviceTree.dtb; load mmc 0:1 0x88080000 initramfs`
    (Set environmental variable _com1_ to _load mmc 0:2 0x82000000 /boot/uImage; load mmc 0:2 0x88000000 /boot/deviceTree.dtb; load mmc 0:1 0x88080000 initramfs_)

    `run com1`
    (This command runs the given commands one after the other)

***

[Back to Table of Contents](../Notes.md)
