testmega.c - > for testing and calibrating RFM22 with Atmega16.Master node connects directly to PC, others need RS232 adapters. Very crude, but works.Connection parameters: 115200, no parity check, 8 data bits, 1 stop bit, no flow control.Setup control by DIP switches as follows.Use DIP switches 1 to 4.

Setup no.	DIP	kbit/s	 Δf [kHz]

0		0000	20	40
1		0001	2,4	4,8
2		0010	2,4	36
3		0011	4,8	4,8
4		0100	4,8	45
5		0101	10	5
6		0110	10	40
7		0111	20	10
8		1000	40	20
9		1001	40	40
10		1010	100	50
11		1011	100	300

Supported commands:

D - read all 128 registers of RFM22 
R xx - read register content on address xx, where xx is in hex
W xx yy - write yy value on address xx, where xx and yy are in hex

S - stop TX, go to READY mode
T - start TX

F - select frequency modulation (FSK)
G - select gaussian frequency modulation (GFSK, BT=0.5)
O - select discrete amplitude modulation (ASK,OOK)
C - select  carrier only (CW)
P - transmit with modulation source ->data from PN9 random number generator
N - transmit with modulation source ->data from internal buffer

1 - test packet mode-> start transmitting packets of predefined structure
2 - test packet mode-> start receiving packets of predefined structure
