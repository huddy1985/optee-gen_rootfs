#
# Original work by Jeff Garzik
#
# External file lists, symlink, pipe and fifo support by Thayne Harbaugh
# Hard link support by Luciano Rocha
#

TARGET=gen_init_cpio
SRC=gen_init_cpio.c
OBJS=gen_init_cpio.o

CC=gcc

$(TARGET): $(OBJS)
	$(CC) $(OBJS) -o $@

%c.%o:
	$(CC) $<

install:
	cp $(TARGET) /usr/bin/$(TARGET)

.PHONY: clean
clean:
	rm -rf *.o $(TARGET)
