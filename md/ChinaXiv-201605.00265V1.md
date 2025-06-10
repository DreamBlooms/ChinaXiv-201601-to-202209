# AN ETHERNET INTERFACE SOLUTION OF SPACE SCIENCE EXPERIMENT PAYLOADS

Tianxiang Jia '， Wenbo Dong ² National Space Science Center, Chinese Academy of Sciences, Beijing, China Technology and Engineering Centre for Space Utilization, Chinese Academy of Sciences, Beijing, China jiatianxiang@nssc.ac.cn, wbdong@csu.ac.cn

# ABSTRACT

In order to dynamicly monitor and manage the working state of space science experiment payloads, the large volume of science data should be performed for real-time transmission. According to this requirement, the paper proposes a design scheme of main information network based on Ethernet. A microprocessor TMS320F2812 and the Ethernet interface chip KSZ8851 are applied to set up the Ethernet communication module of the payloads. The paper illuminates the hardware realization of the scheme with these two chips,as well as the software which is composed of drivers of transceiver register, the data definition of the telemetering data format and the data packing upon UDP/IP protocol. UDP protocol allows the fastest and simple way of transmitting data to the receiver. CCSDS packet format as a standard protocol in space data transformation is adopted in the UDP data packets. The experiment results show that the communication module can successfully transmit the data between Science Experiment Payloads and LAPTOP(or Data management unit) with a good real-time performance in the simple pointto-point circumstance.

Index Terms- Space science experiment payloads, DSP,Ethernet interface,KSZ8851,UDP protocol

# 1.INTRODUCTION

Chinahavebeen developed manyspacescience experiments in the area such as space bioscience,fluid physics,material science and fundamental physics.In these space science projects， real-time data collection and transformation system is required to monitor engineering parameters and scientific data.There are several methods about science experiment data transmission on-orbit. Following with the commercial Ethernet technology's maturation,Ethernet technology has been adopted on the international space station to achieve the communication function in ISS [1].

Considering the mature technology, simple structure and flexibility of Ethernet,China is also advancing the research and application of Ethernet technology on the space science experiment payloads [2].

One of our science experiment payloads have been applied the Ethernet communication technology.As shown in the figure 1,the payloads are connected to the switch through Ethernet interface,then performing the packed science data transmission by Ethernet communication protocol. The data can either be sent downlink to ground for processing,storage and analysis,or displayed directly in the astronaut's laptop or data management unit.

![](images/3c616ec1dee99b84cc581c3bc500467510336790a0cc2687aef9a5791e0b6fc4.jpg)  
Fig.1.Communication framework of one space science experiment payloads.

Actually, the internet interface design is a relatively complicated course.The TCP/IP protocol's demand of its solution makes the conventional circuit less scientific and undesirable.The technique of digital signal processor(DSP) is one of the typical representatives of modern intelligent signal processing technology developed in recent years, whose products havebecome into serialization and diversification.Therefore we present a scheme that applies TMS320F2812 as microprocessor and KSZ8851as Ethernet interface in our Ethernet communication module of space science experiment payloads,both chips are widely used in the civilian and also have corresponding high-grade deviceswhich satisfy the reliability requirementsof Aerospace.

# 2.THEDESCRIPTIONOFHARDWAREDESIGN

# 2.1 The description of TMS320F2812

TMS320F2812,which was performed by TI Company in 2003，is a high performance 32 bit fixed-point DSP controller. So far, it is becoming one of the most advanced processor in control field. TMS320F2812 has some unique characters as followings:

150MHz,150MIPS,32-bit fixed point digital signal processor,which can improve the control system response speed and handling precision. On-chip memories contains up to $1 2 8 \mathrm { K } { \times } 1 6$ FLASH and up to $1 8 \mathbf { k } \times 1 6$ SARAM as well as 4K ROM,a 16 channels 12 bit high-speed ADC. 1.8V core voltage,3.3V I/O voltage, the loss is very low. $\bullet$ Peripheral modules: Event Manager,SCI,SPI, eCAN, McBSP etc. DevelopmenttoolsincludeANSI $\mathrm { C / C ^ { + + } }$ Compiler/Assembler/Linker, CodeComposer Studio IDE，DSP/BIOS,JTAG scan controller. Programmer may develop application in highlevel program language such as C language and $C { + } { + }$ language. It will reduce the cycle of software design greatly and ensure realization of the highest compiling efficiency [3].

Addition， TMS320F2812alsoprovidesexternal interface(XINTF)which adopts non-multiplexed asynchronous bus to expand external devices.An XINTF zone is a region in the DSP memory map that is directly connected to the external interface.The external address bus,XA,on the DSP memory is 19 bits wide and is shared by the entire zone. What external addresses are generated depends on which zones are being accessed.XINTF can expand the off-chip memory and external peripherals [4]. In our space science payloads system， the network controller KSZ8851 is expanded to DSP through XINTF, thus realize the Ethernet communication of the system.

# 2.2The introduce ofKSZ8851

KSZ8851 is a single-port Ethernet controller chip produced byMicrel Inc,whichimplementsthefunctionsofEthernet media access layer(MAC) and physical layer(PHY). The KSZ8851 integrates a Fast Ethernet MAC/PHY with an 8/16/32 bit generic host processor interface and SPI interface. The device has l8KB of internal buffer memory shared between the RXQ and TXQ. The buffer memory on the receive queue is 12KB while the buffer memory for the transmit queue is 6KB.It supports a variety of interface with the embedded micro-controller and microprocessor (MPU). The advantages include small size，low power consumption,flexible configuration and ease to use.It is worth mentioning that KSZ8851 has a corresponding military temperature grade device of COTS thus suitable for the space science experiments.

![](images/1c00df149fffa0e41acf307be62822936e0e3c05d6f12f96a4ba2a0a3f32de27.jpg)  
Fig.2.KSZ8851 block diagram.

The features and descriptions of KSZ8851 are mainly shown as follows:

$\bullet$ Signal chip 10BASE-T/100BASE-TX Ethernet controller with IEEE $8 0 2 . 3 \mathrm { u }$ support.   
$\bullet$ Supports IEEE $8 0 2 . 3 \mathrm { x }$ full-duplex flow control and half-duplex back pressure collision flow control.   
$\bullet$ Signal bus timing for register and data accesses.   
$\bullet$ Flexible 8-bit, 16-bit,32-bit generic host processor interfaces and SPI host interface.   
$\bullet$ Support both big-and little-Endian processors.   
$\bullet$ Support TCP/UDP/ICMP/IPv4/IPv6 32-bit CRC checksum generation and checking [5].

# 2.3 The hardware interface design

KSZ8851 is a low-power CMOS processor that features a signal 3.3V power supply with options for 1.8V,2.5V and 3.3V VDD I/O,so it can connect directly to the pins of TMS320F2812.The system is composed of several units including the main DSP core,the power supply, the reset circuit, the main clock circuit and other interface units.The pins RD and WR of the main DSP core TMS320F2812 are connected to the pins and WR of KSZ8851 respectively as shown in Figure 3.The P1LED1 of KSZ8851 is the mode selection pin,16-bit bus mode is selected when the pin NC or pull-up,8-bit bus mode is selected when the pin pulldown. We adopt 16-bit bus mode in our design.The pins of KSZ8851 that connected to DSP mainly include 16 bits data bus，RD,WR and CS.CS is connected to the XZCS0ANDl pin of DSP that enable KSZ8851 to become an external expansion address area.CMD of KSZ8851 is connected to the GPIOB1O pin of DSP，when common input is low, the access of shared bus is for data access,but when common input is high,and the access of shared bus is for address access. And then, the linkage between receiving signal line $\mathrm { R X ^ { + } }$ ，RX-and transmit signal line $\mathrm { T X ^ { + } }$ TX- was realized by connecting the Ethernet crystal-hand RJ45 through the isolation transformer. The major effect of the isolation transformer is to insulate the embedded system and External line and to realize hot plug function [6].

![](images/e0bbd047d4453f545a8fe440a5bf2ca51b422bebc711b0400a82ad03b33d237d.jpg)  
Fig.3.The block diagram of communication module.

# 3.THESOFTWAREDESIGNOFETHERNET COMMUNICATION

# 3.1 The flow chart of the software overall design

DSP controls the running of the entire system as the master CPU.After system power on,as shown in the figure 4, KSZ8851 initialization is first performed by processor through the bus line, then the communication module enter the data transceiver waiting state.The science data is encapsulated by the upper layer protocol and then transmitted to the send buffer of KSZ8851 byte by byte. When the send command is enabled, KSZ8851 packets the MAC data frame and transmits them automatically.While receiving the Ethernet data frame,the main processor tests the validity about them,if the header is incorrect or CRC error, the frame is discarded, otherwise save the correct data frame and then sends them to the upper layer.

![](images/e39c5e91662a66aaf60dd76f985cce760b67bea14d0a037870a8db4b7709fbba.jpg)  
Fig.4. Software flow of Ethernet communication.   
Fig.5.CCSDS packet format of data from isolation platform to LAPTOP.

The software of the design is mainly composed of the underlying network card driver, the packing of CCSDS telemetry data and the realization of the embeddedUDP/IP stack.

# 3.2The software control ofKSZ8851

In order to start the network controller KSZ8851 at the ready state about data transceiver,we must process the initialize configuration. All of control and status registers in KSZ8851 are accessed indirectly depending on CMD pin The command sequence to access the specified control and status register is to write the register's address(when $\mathrm { C M D = 1 }$ ）then read or write this register data(when ${ \mathrm { C M D } } { = } 0 _ { \cdot } ^ { \cdot }$ ）

KSZ8851 initialization steps are as follows: $\bullet$ SettheMAC address ofKSZ8851.   
$\bullet$ Enable the data transceiver pointer.   
$\bullet$ Set the transceiver control register.   
$\bullet$ Set the interrupt state/enable register.

The inner part of KSZ8851 contains 18KB SRAM which is used as the data transceiver buffer,among them there are 6KB send data buffer and 12KB receive data buffer.Read the chip ID $\phantom { + } 0 \phantom { + } \times 8 8 7 0$ correctly at first and then set the critical register,KSZ8851 will be startup correctly in the working state.If it restarts because of an abnormal phenomenon, the same operation should be processed again to recover it to normal. When detecting the data send signal, the data package in send buffer is treated as the Ethernet data packet and then sends out. When receiving the data, KSZ8851 will generate a data receive interrupt， the interrupt service routine read out the received data packet and then put them to the upper protocol [7].

# 3.3 The software control ofKSZ8851

CCSDS standard has become widely used as a basic document that each country and institution of the international space community enacting and implementing the application standard itself.The valid data of the space science experiment payloads adopt CCSDS standard, they locate in the DATA district of UDP datagram, the entire length is 1024bytes.As shown in the figure 6, the CCSDS source packet type is composed of packet dominant header and packet data.

<html><body><table><tr><td colspan="5">Packet dominant header,6 bytes （48bit）</td><td colspan="2"></td><td colspan="2">Packetdata</td></tr><tr><td rowspan="2"></td><td colspan="3">Packet data</td><td colspan="2">sequence control</td><td rowspan="2"></td><td rowspan="2">Packet asstant header Pal Aided data,</td><td rowspan="2">Source</td></tr><tr><td>Type 0</td><td>Assistant</td><td>flag</td><td>apication identifier</td><td>sign ecounter Group</td><td></td></tr><tr><td>3bit</td><td>lbit</td><td>1bit</td><td>11bit</td><td>2bit</td><td>14bit</td><td>16bit</td><td>variable</td><td>variable</td></tr></table></body></html>

The packet dominant header that account for 6 bytes is composed of package identifier(16bit),package sequence control(16bit),package size(l6bit). The package identifier consists of package version number (3bit)，type (lbit), assistant dominant header sign (1bit)，and application process identifier (11bit).The package sequence control consists of group sign (2 bit) and package sequence counter (14bit). The package size (l6bit) indicates the entire byte number from the first byte of assistant dominant header to the end of the package.Packet data is composed of packet assistant dormant head and source data strict.The assistant header flag of the packet dominant header determine the existence of the packet[8].The science data about the space experiment payloads working state arelocated in the source data strict.

# 3.4 The software design of upper communication protocol

TCP/IP is the fundamental communications protocol of the Internet. TCP and UDP are two protocols of TCP/IP transmission layer protocol. The application decides which transport protocol is used.UDP is a transport layer protocol that provides connection-less delivery service in OSI Reference Model.TCP is a reliable,connection-oriented protocol that provides error checking and flow control function. TCP is capable of detecting congestion in the network and will back off transmission speed when congestion occurs.These features protect the network from congestion collapse.Unfortunately due to the fact that TCP isareliable service,delays will be introduced whenever a bit error or packet loss occurs.This delay is caused by retransmission of the broken packet, along with any successive packets that may have already been sent. This can be a large source of jitter that rendering TCP unusable for real-time services.For these reasons we use UDP for the data transmission.UDP allows the fastest and most simple way of transmitting data to the receiver. There is no interference in the stream of data that can be possibly avoided. This provides the way for an application to get as close to meeting real-time constraints as possible [9].In addition, CCSDS packet format is adopted in theUDP data packets that check the consistency during the data transceiver and guarantee the controlling of the data sequence.

The process of the data packing is shown as figure 6, firstly theUDP frame head isadded to the initial data about the message of payloads,which includes source port, destination port, the length of UDP data and the checksum. Secondly the IP head is added,which includes source IP address,destination IP address,IP data length,checksum etc.Finally the Ethernet frame format is encapsulated accord with IEEE802.3 standard which is composed of the destination MAC address,source MAC address and the length ofEthernet frame.The source MAC address is the local physical address and has been set in the initialization program. The CRC checksum of the IEEE802.3 frame structurewouldbeaccomplished automaticallyby KSZ8851.

![](images/432d54e9ec9c3953571493f87198da37f954c8e62d5d2418e5208d1b80f4c70a.jpg)  
FIg.6.Package structure ofEthernet format based on UDP.

Unpacking data can be taken as the inverse process of packing.As shown in the figure 7, the micro-controller DSP analyzes the datagram in different methods according to the different header of them. When KSZ8851 has receivedanEthernetdataframeindatalinklayerand save them in the array， firstly estimate the type of the data frames.If ARP packet,add the information to ARP table.If IP packet, comparing the received IP address to the local IP address and testing the checksum meanwhile,DSP receives the datagram if the IP address are the same,otherwise discards it.If the checksum is not correct,it indicates that some error occur during the transmission, the IP datagram should be discarded also,but does not generate the error message packet [10].

![](images/16a8c16b0cdf552b9e5a89ba1f96c1262f5557c48f8b21ab3e0bd1c3d57c52ec.jpg)  
Fig7.Flowchart of receiving data.

# 4.THEANALYSISOFTHETESTRESULT

During the test,we use network analyze software Wireshark to catch the procedure ofUDP communication between the Ethernet module of the payloads and the upper computer. The ARPlink testis performed firstly.Figure 8 isa screencapture of the data frame that displays the sequence of the ARP and UDP.The micro-controller DSP send an ARP request to the upper computer, after the request is received, the computer will send out an ARP reply that includes its MAC address,and then the communication is established.

Analyzing one of the captured UDP datagram，we conclude that the destination MAC address is $^ { \mathrm { ~  ~ } } 0 0 \ 1 5 \ \mathrm { c } 5 \ 3 \mathrm { e }$ $1 1 ~ { \mathrm { c } } { \bar { 5 } } ^ { \prime \prime }$ ,which is the MAC address of the upper computer. The source address is“20 O1 33 31 8f 5a”which is also the MAC address of the base board.The test IP address of the LAPTOP is“193.168.1.40” while the IP address of the base board is“192.168.1.11”,the source port and the destination port are all “2100”. The CCSDS telemetering data packet is in the data strict of the captured datagram.

Broadcom 440x10/100 Integrated Controller:Capturing-Wireshark DOX  
EeEdit Telepho [ools Help  
1 QQQ 区 % 面  
Fiten Expression Cleag Apply  
No.. Time Source Destination Protocol Info □655645.445533 20:01：33：31:8f:5a Broadcast 脚印 whohas192.168.1.402Te11192.168.1.11656645.445558 Del1_3e:11:c5 20:01：33:31:8f:5a 192.168.1.4015at00:15:5:3:11:5657646.447703 192.168.1.11 192.168.1.40 UDP Sourceport:aniganetfs Destination port: aniganetfs659 660648.447705 192.168.1.11 192.168.1.11 168.192.1.40 168.192.1.40 信## Source port:aniganetfs Source port: aniganetfs Destinatfon port: aniganetts aniganetfs661 649.447704 192.168.1:11 188 183-18 Sourece portgantts Destatonportgs  
8 87-8 13：18831 188183:148 SOuFEE POrtTgn Destinat1on aniganetfs iganetfs192:181:11 168.183:1:48 SOur P Destination anganets667655.447 192.168.1.11 Source port:anlganetfs aniganets669657.447738 668 656.447739 192.168.1.11 192.168.1.11 168.192.1.40 Sourceport: Source port:aniganetfs aniganetfs Destination port: Destination aniganetfs aniganetfs670 658.447738 192.168.1.11 168.192.1.40 Source port: iniganetrs Destination ganetrs 1国  
Frane78（170bytesonwire,170bytescaptured)  
EthernetII，Src:20:01:33：31:8f:5a（20:01:33:31:8f：5a），05t:De11_3e:11:c5（00:15:c5:3e:11:c5)  
InternetProt0co]，5rc:192.168.1.11（192.168.1.11），0st:168.192.1.40(168.192.1.40）  
UserDatagranProtocoT，SrcPort:amiganetfs(21o0)，Dst Port:aniganetfs(2100)  
Data(128 bytes)  
000 08004500 ...>.. . 平

# 5.CONCLUSION

According to the communication requirement ofspace science experimentpayloads， thepaper detailedly introduces an design of an Ethernet interface based on TMS320F2812 and KSZ8851 and analyzes the software function in this DSP and transceiver drivers ofKSZ8851.In this system，the Internet Protocol,the Internet Control Message Protocol, the Address Resolution Protocol, the

Reverse ARP，the Transmission Control Protocol，the CCSDS Packet Telemetry format and the User Datagram Protocol are all be realized. The results of experiments demonstrate that the performance of this Ethernet interface design is stable. This design is a concise construction, which can be realized easily in most embedded system and can be used in many applications for the Ethernet communication between data management unitsand experiment payloads in the future.

# REFERENCES

[1] C.A.Evans，J. A.Robinson，J. Tate- Brown，T. Thumm， J. Crespo-Richey. D. B. Baumann,J. Rhatigan. International space station science research accomplishmentsduringthe assembly years:an analysis of results from 2000-2008.[R] NASA/TP2009-213146-Revision A. 2009   
[2]Yidong Gu, Ming Gao, Guangheng Zhao, Jiong Guo. Utilizations in China manned space engineering[C]. IAC-09-B3.4.5.2009.   
[3] Texas InstrumentsIncorporated. TMS320F2810, TMS320F2811，TMS320F2812, TMS320C2810, TMS320C2811，TMS320C2812 Digital Signal Processor Data Manual. TI, 2007.   
[4] Texas Instruments Incorporated. $\mathrm { T m s } 3 2 0 { \bf x } 2 8 1 { \bf x }$ DSP External Interface(XINTF) Reference Guide.TI.   
[5] Micrelincorporated. "KSZ8851MQL/MLL/SNL Product Brief Single Port MAC/PHY Controller with Non PCI Interface".Micrel, 2009.   
[6] $\mathrm { Y u }$ -duo Wang,Xiao-miao Dai,“A Ethernet Interface Solution Based on TCP/IP Protocol ”. In proceedings of the 2O12 IEEE International conferrence on Signal Processing.Beijing, China,2012,pp.1521\~1525,2012.   
[7]Micrel incorporated. “KSZ8851-16MLLJ Single-port Ethernet controller with 8-bit or 16-bit Non PIC interface Data sheet".Micrel, 2009.   
[8] Dong-mei Du,“Processing Method of the Telemetry Data Packet for Spacecrafts”, Telecommunication Engineering, vol 47, no 2, pp.176-180,2007.   
[9]Behrouz A.Forouzan，TCP/IP Protocol Suite，Third Edition.Beijing: Tsinghua University,2006.   
[10]Richard Stebens W.TCP/IP illustrated volume 1:the protocol. Translated by Fan Jianhua, Xu Guanghui, Zhang Tao,etc.Beijing: Machinery Industry Press, 2000.