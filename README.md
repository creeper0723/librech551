LibreCH551
----------

An __open-source__ command line flasher program and SDK library for WCH(Nanjing QinHeng Corp.)'s CH55x family.
[Our Wiki contains a lot of useful tips, it's worth to check out!](../../wiki/Home)

The CH55x is a series of 8051 microcontroller with dedicated USB peripheral. CH553/CH554 can be programmed as a USB host.
The cheapest one, CH551 only costs 1.5 CNY in retail. It is the ultimate and ideal solution for many low-end USB applications.

Up to now, we have tested out CH551 and CH554, all functions work fine except option byte.

If someone want to help me, please __start__, __fork__ and support more chips, Thanks!


TODO
------------
Implement chip programming via UART for devices workign on USB Host mode. (It is very simple to realize: just add serial port interface to the program and 0x619e, accumulate checksum in packet tail).

Implement new CH55x ISP protocol (for bootloader version > 2.30), for now we don't have any chip shipped with the new bootloader: WCH's FAE said that they will release chips with new bootloader after Apr.2018.

__Contributions are always welcome__

Command Line Parameters
------------
* __-f \<filename\>__ Erase the code flash and download binary codes to CH55x, note that this tool only accepts `.bin` files, `.hex` files will not be accepted.
The Eclipse SDCC environment with the setup [described in our wiki](../../wiki/Setup-SDCC-developing-environment-with-Eclipse) automatically generates `.bin` file. To convert a hex file to bin file, on Linux, use `objdump`, on Windows, use `hex2bin.exe` in [`win_tools.zip`](../../wiki/win_tools.zip).
* __-g__ Execute the user program after downloading
* __-e__ Erase chip only
* __-D \<filename\>__ Read data flash to a file
* __-d \<filename\>__ Write the content of a file to data flash
* __-h__ Display help message

For macOS Users
----------

* libusb install `brew install libusb`
* Build: Type `make` in `usbisp` directory.
* Install:Type `sudo make install` in `usbisp` directory, you can also pass DESTDIR to the script to set installation path. 

License
----------

GPLv3

Author(s)
----------

[Zhiyuan Wan](https://github.com/rgwan) <h@iloli.bid>

[Rikka0w0](https://github.com/rikka0w0)
