GPS tracker with a simple LCD interface
==================================================

After much negative experience with Android GPS tracking (battery usage, bad
reception) I decided to build my own dedicated GPS tracker despite the fact that
multiple similar devices are readily available on the market.




Selected components
----------------------

  * Quectel L70B GPS receiver module with low power tracking function. They claim
    1.4mA tracking current draw under static conditions. We will see.
  * STM32F401 microcontroller in a QFN48 package, low power run mode
  * EA DOGS 102x64px graphic LCD module with low power consumption (0.25mA)
  * USB connections for charging and downloading data
  * SPI serial flash for data storage (8Mbit/16Mbt)
  * 600mAh 3.7V LiPo cell



Battery and memory size
----------------------------

The goal is 5mA current draw which should be enough to provide nearly 4 days of
continuous logging using the mentioned 600mAh LiPo cell. Such cells are
available in local stores or on eBay.

The following items will be saved:

  * 32 bits for the actual time
  * 32 bits for latitude
  * 32 bits for longitude
  * 16 bits for height
  * 16 bits reserved for header and other data

Which gives 16 bytes for a single point or 65536 points in a 1MB flash memory.
Considering 5 second logging interval (should be enough fir hiking), the flash
memory should suffice for 91 hours of logging, which is nearly 4 days.



Project status
------------------

As of 2016-02-06, basic requirements are determined and the schematic is ready.
Board layout is WIP.



Bill of materials
----------------------

TODO



Schematic and layout pictures
----------------------------------

[schematic](doc/schematic.png)



Prototype photos
-------------------

TODO



Resources
--------------

You can access the schematic/layout files and firmware at
[https://github.com/iqyx/lcd-gps-tracker](https://github.com/iqyx/lcd-gps-tracker)
