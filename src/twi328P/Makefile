#
#
#	Makefile
#	
#	target: prerequisites prerequisites ...
#		<tab>command
#		<tab>command
#
#	$@	=	target name
#	$?	=	all prerequisites newer than target
#	$<	=	first prerequisites
#	$^	=	all prerequisites
#
#	The @ in front of the echo command, prevents the actual command from being printed to screen
#
#	$(patsubst PATTERN,REPLACEMENT,TEXT)
###############################################################################
#
#	Misc. defs
#
#PORT		= usb-0000
DEVICE		= atmega328p

ifndef CPU_FREQ
	CPU_FREQ	= 16000000UL
endif

#PROGRAMMER	= atmelice_isp
#BAUD		= 115200
#BAUD		= 9600

#	define target name
TARGET = twi328P

#	define compiler and various options for this
CXX		= avr-g++ -c
INCLUDEPATH	= -I../../inc/ -I/home/jole/.arduino15/packages/arduino/tools/avr-gcc/7.3.0-atmel3.6.1-arduino7/avr/include/
C_FLAGS		= -c -Wall -Os -mmcu=$(DEVICE)

#	source- and destination files directories
INCDIR = inc
SRCDIR = src
OBJDIR = obj
LIBDIR = /home/jole/mnt/projects/avr-lib/lib
###############################################################################

$(OBJDIR)/$(TARGET).o : twi328P.cpp
	$(CXX) -c -g -Wall -Os -mmcu=$(DEVICE) -o $(OBJDIR)/$(TARGET).o $(INCLUDEPATH) twi328P.cpp
	avr-ar rcs $(LIBDIR)/twi328P-lib.a $(OBJDIR)/$(TARGET).o
