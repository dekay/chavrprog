# chavrprog
AVR programmer using  Chinese ch341a chip

There is a lot of strange things from China, and ch341a is one of the them. Cheap USB-Serial, USB-SPI, USB-I2C, USB-Parralel, etc makes it seems to be the real thing. However, lack of documentation make that device almost useless, except for couple of open-source projects. This project adds support for AVR microcotrollers programming using CH341a chip/

Project is based on ch341prog by Setarcos (https://github.com/setarcos/ch341prog), and technically is a brief implementation of ATMEL
serial programming protocol using low-level functions from ch341prog project.
Also, to parse Intel HEX source files from libcintelhex (https://github.com/martin-helmich/libcintelhex) are used.



Usage
---------
-r ADDR - read flash memory from start to ADDR in words (max addr = capacity in bytes/2)
-w HEX - write flash memory from intel HEX file
-e - erase devices
-c HEX - read and compare HEX with flash memory
-a HEX - automatically erase, write and check data in chip
-f - read fuse bits
-l BYTE - write low fuse
-h BYTE - write high fuse
-x BYTE - write extended fuse
-L read lock bits

Project is under development and unstable!!!
To add another MCU's it's necessary to change definition in main.c file. Theoretically, current version should work with any Atmega chip, but was tested only with on Atmega32u4. Implementation for Attiny devices may need to change SPI programming commands and bit shifting in functions.

License
------------
This is free software: you can redistribute it and/or modify it under
the terms of the latest GNU General Public License as published by the
Free Software Foundation.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License
for more details.

You should have received a copy of the GNU General Public License along
with this program. If not, see <http://www.gnu.org/licenses/>.