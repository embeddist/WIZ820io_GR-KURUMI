WIZ820io_GR-KURUMI
==================

# WIZ820io
WIZ820io provides easy and simple Ethernet connectivity to small platforms like GR-KURUMI (Compatible with Arduino Pro Mini). 
WIZnet W5200 ethernet chip is used in WIZ820io. 
To use WIZ820io with GR-KURUMI, users need to replace 4 files in the Ethernet library for GR-KURUMI.


![WIZ820io](http://www.wiznet.co.kr/Admin_Root/UpLoad_Files/ProductImgs/Lst_1160_20111027110621.jpg "WIZ820io")

## HW



## Software
You need to change the existing W5100 files to W5200 library files.

1. Install W5200 library
   Overwrite w5100.cpp, w5100.h to the "/libraries/Ethernet/utility" folder in your Arduino IDE. 

2. Using the W5200 library and evaluate existing Ethernet example.
   In the Arduino IDE, go to Files->Examples->Ethernet and open any example, compile and upload the file to Arduino board.

3. Note: libraries/Ethernet/Ethernet.h needs the following at line 10 instead of #define MAX_SOCK_NUM 4, since it doesn't #include "w5100.h" anymore:

 `#ifdef W5200`

 `#define MAX_SOCK_NUM 8`

 `#else`
 
 `#define MAX_SOCK_NUM 4`

 `#endif`



## Revision History
Initial Release : 10 June 2013
