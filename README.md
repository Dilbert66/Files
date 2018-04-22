# Files
Modified Dual boot (serial/usb) bootloader from the Multiprotocol 4in1 project to work with the 1st generation IrangeX pro 4in1 module 
that did not have the  usb port.  This module version has a defect in the inverter circuit that only allows it to work with inverted comms. Since the current bootloader included with the latest Multiprotocol distribution sets up the module to use non-inverted receive communications, this won't work with those problematic modules. 
This bootloader version instead uses inverted rx comms and also fixes an issue with some modules not booting correctly in the taranis.  The source for the bootloader is hosted on Mike Blandford's repository at: https://github.com/MikeBland/StmDualBoot.  I've posted the file I modified (SerialLoader.c) here from the repository for reference.
 The invert version is mainly for the 1st generation irangex pro (while it will also work with all modules)  while the noninv is simply a fix for the bootup problem on the taranis for those that don't want to use the inverted comm option when flashing when using other modules.
 
 
 
To use the invert version, you will need to insure you select inverted comm as YES in the flashing application.

To flash, if using windows run the stm32flash utility from the "DIY-Multiprotocol-TX-Module\BootLoaders\Boards\stm32\tools\win" directory.

stm32flash -v -g 0x0 -b 57600 -w \path_to_file\stm32dualboot_inv.bin COMx   

where comx is the com port of your ftdi adapter and \path_to_file\ is the full path of the location of the bootloader file

NOTE: You WILL need to re-flash the Multiprotocol.bin to your module after updating the bootloader since it clears everything.
NOTE ii:  Ensure you use the latest Multi Flash App from Mikes ersky9x thread at: http://openrcforums.com/forum/viewtopic.php?f=7&t=4676



