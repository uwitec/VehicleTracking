INCLUDE_FLAGS = -I. -I../include -I../GPS/nmea -I../protocol/include
CFLAGS	      = $(INCLUDE_FLAGS) -Wall -g
CC			  = arm-linux-gcc

AR			  = arm-linux-ar
AFLAGS		  = -r

TARGET = libalarm.a

SOUCE_FILES = $(wildcard *.c)
OBJS = $(patsubst %.c,%.o,$(SOUCE_FILES))

%.o : %.c %.h
	$(CC) -c $(CFLAGS) $< -o $@

%.o : %.c
	$(CC) -c $(CFLAGS) $< -o $@

$(TARGET): $(OBJS)
	$(AR) $(AFLAGS) $(TARGET) $(OBJS)

.PHONY:clean
clean:
	$(RM) $(TARGET) $(OBJS)
