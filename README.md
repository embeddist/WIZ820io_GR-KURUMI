# WIZ820io
WIZ820io provides easy and simple Ethernet connectivity to small platforms like GR-KURUMI (Compatible with Arduino Pro Mini). 
WIZnet W5200 ethernet chip is used in WIZ820io. 
To use WIZ820io with GR-KURUMI, users need to replace 4 files in the Ethernet library for GR-KURUMI.

![WIZ820io](http://www.wiznet.co.kr/Admin_Root/UpLoad_Files/ProductImgs/Lst_1160_20111027110621.jpg|300 "WIZ820io")

[GR-SAKURA - Forum, GR-KURUMI](http://renesasrulz.com/app_kits_and_demo_boards/gadget_renesas_user_forum/f/128/t/3968.aspx)


## Hardware
![WIZ820io_GR_KURUMI](https://raw.github.com/embeddist/WIZ820io_GR-KURUMI/master/Hardware/wiz820io_gr_kurumi.png "WIZ820io_GR_KURUMI")
*PWDN, nINT signals are not used.*

## Software

#### Install W5200 library
   Download modified w5100.cpp & w5100.h and files (attached) and overwrite onto the"RLduino78/libraries/Ethernet/utility" folder in your project in e2studio. 
   
* Uncomment a below line in the modified w5100.h 

`#define W5500_ETHERNET_SHIELD` 

* Change MAX_SOCK_NUM as 8 on Ethernet.h in RLduino78/libraries. 

`#define MAX_SOCK_NUM 8` 

#### SPI Configuration

* Set SPI Mode as Mode0 and change the SPI.h in " RLduino78/libraries/SPI" as below, 

`#define SPI_MODE_MASK 0x0000;`

* Set SPI Clock Divider (@16MHz)and change the in SPI.c in "RLduino78/libraries/SPI " as below, 

`SPI_SDRxx     = SPI_CLOCK_DIV2 << 9;`


## Using the W5200 library and evaluate existing Ethernet example.
All other steps are the same as the steps from the Arduino Ethernet Shield. You can find examples in the Arduino IDE, go to Files->Examples->Ethernet, open any example, then copy it to your sketch file (gr_sketch.cpp) and change configuration values properly.
After that, you can check if it is work well. For example, if you choose 'WebServer', you should change IP Address first and compile and download it. Then you can access web server page through your web browser of your PC or something.

## Revision History
Initial Release : 28 July 2013
