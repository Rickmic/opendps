BINARY = dpsboot

# The baudrate used for serial communications, defaults to 9600
BAUDRATE ?= 9600

GIT_VERSION := $(shell git describe --abbrev=4 --dirty --always --tags)
CFLAGS = -I. -I../opendps -DGIT_VERSION=\"$(GIT_VERSION)\" -DCONFIG_PAST_NO_GC -DCONFIG_BAUDRATE=$(BAUDRATE)
# Future optimisation: saves ~600 bytes but does not work for gcc <= 7
#CFLAGS += -flto

OBJS = \
	common.o \
	hw.o \
	dpsboot.o

# Bootloader linker script
LDSCRIPT = stm32f100_boot.ld

#include ../stm32common/makefile.inc
include ../libopencm3.target.mk
