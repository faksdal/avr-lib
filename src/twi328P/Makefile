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
CPU_FREQ	= 16000000UL
#PROGRAMMER	= atmelice_isp
#BAUD		= 115200
#BAUD		= 9600

#	define target name
TARGET = twi328P

#	define compiler and various options for this
CXX		= avr-g++
INCLUDEPATH	= -I../../inc -I. -I/home/jole/.arduino15/packages/arduino/tools/avr-gcc/7.3.0-atmel3.6.1-arduino7/avr/include/
C_FLAGS		= -g -Wall -Os -mmcu=$(DEVICE)

#	source- and destination files directories
INCDIR = inc
SRCDIR = src
OBJDIR = obj
BINDIR = bin
###############################################################################



###############################################################################
#	generate file lists for the compiler/linker
SOURCES = $(wildcard *.cpp $(SRCDIR)/*.cpp)
OBJFILES = $(patsubst %.cpp, $(OBJDIR)/%.o, $(notdir $(SOURCES)))
###############################################################################



###############################################################################
#	Rule to link all object files
#link: $(OBJFILES)
$#(TARGET): $(OBJFILES)
#	@echo "Link section: "$(OBJFILES)
#	$(CXX) -mmcu=$(DEVICE) $(OBJFILES) -o $(BINDIR)/$(TARGET).elf
#	avr-objcopy -j .text -j .data -O ihex $(BINDIR)/$(TARGET).elf $(BINDIR)/$(TARGET).hex
#	avr-size --format=avr --mcu=$(DEVICE) $(BINDIR)/$(TARGET).elf
	#$(CXX) $(C_FLAGS) -o $(BINDIR)/$(TARGET) $(OBJFILES)
###############################################################################



###############################################################################
#	
#	
$(OBJDIR)/%.o: $(SRCDIR)/%.cpp
	@echo "Build file with main()-function:"
	$(CXX) $(C_FLAGS) $(INCLUDEPATH) -c -o $@ $^
###############################################################################
