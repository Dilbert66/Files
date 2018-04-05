# Files
Modified Dual boot (serial/usb) bootloader from the Multiprotocol 4in1 project to work with the 1st generation IrangeX pro 4in1 module 
that did not have the  usb port.  This module version has a defect in the inverter circuit that only allows it to work with inverted comms.
This bootloader also fixes the issue with some modules not booting correctly in the taranis.  The source for the bootloader comes from Mike Blandford's repository at: https://github.com/MikeBland/StmDualBoot.  I've posted just the changed file (SerialLoader.c) only here from the repository.
There are two versions.  The invert version is for the 1st generation irangex pro while the noninv is simply a fix for the bootup problem on the taranis.
To use, you will need to insure you select inverted comm as YES in the flashing application.

To flash, if using windows run the stm32flash utility from the "DIY-Multiprotocol-TX-Module\BootLoaders\Boards\stm32\tools\win" directory.

stm32flash -v -g 0x0 -b 57600 -w \path_to_file\stm32dualboot_inv.bin COMx   

where comx is the com port of your ftdi adapter and \path_to_file\ is the full path of the location of the bootloader file.



