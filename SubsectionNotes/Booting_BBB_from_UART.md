[Back to Table of Contents](../Notes.md)
***

# Booting Beaglebone Black Board from UART

In this section, we need to make sure Beaglebone black board boots from UART mode, while it is waiting for the bootloaders we will sent the MLO, U-boot, Linux kernel and the Device tree Binary from UART Serially through XMODEX, YMODEX, ZMODEX protocols which we are calling as "Booting from UART".

### Prerequisite to Follow below steps:
* Remove the uSD card from the Board.
* Board shoud be preferably powered through the adapter, because theoritically before UART is checked while booting, it will check the USB port, if the port is connected to the computer then it might assume that the boot image will be sent through it and stay waiting. But when practically checked it was going to UART mode easily!! But this might not be the case always.

For more Information about the U-boot commands and Syntax Refer:
[U-Boot Most Useful commands and Syntax](SubsectionNotes/Uboot_commands.md).

### Steps:

1.

***

[Back to Table of Contents](../Notes.md)

Next: []()

Previous: []()
