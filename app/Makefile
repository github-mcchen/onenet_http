BIN = test

CC = gcc

TOPDIR = $(shell pwd)
INCLUDE := -I$(TOPDIR)/../Inc 
LIB := -L$(TOPDIR)/../Lib/ -lRestFulLinux -losAdaption -lm -g

SRC := $(wildcard *.c)
OBJS := $(patsubst %.c, %.o,$(notdir $(SRC)))

all:${BIN}

${BIN}:${OBJS}
	$(CC) -o $@ $^ $(LIB)
	
${OBJS}:${SRC}
	$(CC) $(INCLUDE) -MD -c $< -o $@
	
.PHONY : all clean
clean :
	@rm -rf $(OBJS)
	@rm -rf *.d
	@rm -rf ${BIN}
	