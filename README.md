USB Data Link Cable API
=======================

2013-10-17   See also: [English](http://www.cnblogs.com/LiuKaiFa/p/USB_data_link_cable_API.html)   [Chinese](http://www.cnblogs.com/LiuKaiFa/p/USB_%e8%81%94%e6%9c%ba%e7%ba%bf_API.html)

KEY:USB Data Link Cable, USB easy cable, USB Data Transfer Cable, USB File Transmitter Cable, USB PC to PC Data Link Adapter Cable, USB Data Link Cable API, SMART KM LINK keyboard and mouse sharing, USB Data Cable, USB shared cable.

1. Overview
-----------
Current computer 's USB port has become commonplace , USB2.0 theoretical transfer rate of up to 480Mbps, ie 60MB/s, USB3.0 theoretical transfer rate of up to 5Gbps, ie 625MB/s. Currently the USB port is mainly used for U disk, USB hard disk, USB keyboard, USB mouse, USB camera , USB CD-ROM¡¢USB DVD drive, etc.

In fact, with a USB data link cable(also called USB shared cable, USB easy cable, USB connection cable, USB interconnection cable, USB copy cable, USB networking cable, etc.) using the USB port can also achieve USB pc to pc communication, USB point-to-point communications, USB point-to-multipoint communications, USB-based small-scale distributed server, USB file transfer, USB CD-ROM sharing, HD data sharing, HD data sync, network sharing, KM(key/mouse) sharing, clipboard sharing, file sharing,etc.

Typically, USB data link cable are configured dedicated software to achieve data sharing, data sync, KM(mouse and keyboard) sharing, clipboard sharing, USB device sharing and other functions. These cables are not providing application programming interface (API), which poses a barrier to developers who want to USB communication, USB file transfer, USB data sharing, USB device sharing, etc. functionality into their own procedures, developers can not implement their own point to point( or points to multi-point ) communication through the USB port. For the needs of developers, Shijiazhuang ZhongZhi Electronic Technology Development Center has developed a USB data link cable application programming interface (API), and provide support for developers to develop their applications. A friend in need, please contact, tel:86-311-87024917, mobile:86-13803113171, QQ:1561724180, email:1561724180@qq.com.

![Image of usb2usbApp](https://github.com/zzkjliu/USB-Data-Link-Cable-API/raw/master/usb2usbApp.jpg)

2. ZhongZhi USB Data Link API
-----------------------------

```
/*****************************************************************************
Filename: zzUsbAPI.h
Function: USB Data Link Cable API(Application Programming Interface).
Editor:   LiuYaoKai
Date:     2012.6.28 2013.7.26

	  Ver1.1  2013.7.26
	  Copyright(C) by LiuYaoKai 86-13803113171 86-311-87024917
******************************************************************************/

int u2u_init()
    DESCRIPTION:
	Initialization API, get the device ID and packet size. maximum packet size is 64K.
    Return Values:
	See the API defined constants related series

BOOL u2u_Open() 
    DESCRIPTION:
	Open the device of USB data link cable.
    Return Values:
	True     success 
	False    failure

BOOL u2u_RecvData(LPBYTE lpBuf, int& len, int& ret)
    DESCRIPTION:
	Receive data from usb.
    Parameters:
	lpBuf
	    [out]Pointer to the buffer that receives the data from the USB port. The size of the receive buffer should be greater than or equal packet size.
	Len
	    [in]Specifies the number of bytes to be receive from the USB port. 
	Ret
	    [out]Return an error code or receive buffer remaining number of 
	Return Values:
	    True    success 
	    False   failure, cause see ret return value.

BOOL u2u_SendData(LPBYTE lpData, int len, int& ret)
    DESCRIPTION:
	Transmit data from usb port
    Parameters:
	lpBuf
	    [in]Transmit data buffer pointer. the transmit buffer size should be less than equal to the packet size. If lpBuf = NULL, the function returns the remaining unprocessed number of packets in the transmit buffer.
	Len
	    [in] Specifies Length of data want to send(in byte).
	Ret 
	    [out]Return an error code or receive buffer remaining number of unprocessed packets.
	Return Values:
	    True    Success 
	    False   Failure, cause see ret return value.

void u2u_Close()
    DESCRIPTION:
	Close USB device of data link cable.

void u2u_Exit()
    DESCRIPTION:
	Unload API. Usb device of data link cable should be closed, then perform this operation. 

DWORD u2u_getLastErr()
    DESCRIPTION:
	Get the last error code of api operation error 

void u2u_FreeTxRxBuf()
    DESCRIPTION:
	Empty the transmit and receive buffers

```

3. About USB data link cable
----------------------------
USB data link cable and ordinary USB cable are different, there is a chip in data link cable middle. Because the USB bus system can have only one host, usually the computer's USB port are the host interface, so you can not simply connect them together. A transformation is needed between PC USB port and PC USB port, the chip in the middle of  cable is to complete this conversion, this has a USB data link cable generation. There is a small pimple in the middle of a USB data link cable, or one end of USB data link cable is similar to the U disk, and some cable itself can also be used as U disk.

1 USB cable linknetworking cable = 2 net card + 1 net wire, and the rate is much faster than the 100M card.
     
USB data link cable applications:
- High speed transfer files or copy files between two computers
- Synchronize files or documents between two computers
- Sharing IP Internet (without card, through another computer on the Internet)
- Shared device(For example: keyboard, mouse,CD-ROM,DVD,etc.)
- USB point-point communication
- USB point-to-multipoint communication
- USB file transfer, USB data transfer
- Small distributed server
- .......


ZhongZhi Electronic Technology Development Center

Address£ºN0.8 Sports Street, Qiaoxi region, Shijiazhuang City,Hebei,China

Tel£º86-311-87024917  86-13803113171
