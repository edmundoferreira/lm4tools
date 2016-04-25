EXE := lm4flash

CC ?= gcc

CFLAGS := -Wall $(shell pkg-config --cflags libusb-1.0)
LDFLAGS := $(shell pkg-config --libs libusb-1.0)

all: CFLAGS += -O2
all: $(EXE)

debug: CFLAGS += -g -DDEBUG
debug: $(EXE)

$(EXE): $(EXE).c
	$(CC) $(CFLAGS) $^ $(LDFLAGS) -o $@

clean:
	rm -f *.o $(EXE)

install:
	cp $(EXE) /usr/bin/

uninstall:
	rm -f /usr/bin/$(EXE)


.PHONY: all clean
