DESTDIR := /usr/local/bin
CC := clang
CFLAGS := -O2

C_INCLUDES = -I/opt/homebrew/Cellar/libusb/1.0.24/include

wchisptool:main.c
	#$(CC) $(CFLAGS) main.c -o wchisptool `pkg-config --cflags --libs libusb-1.0`
	$(CC) $(CFLAGS) $(C_INCLUDES) main.c -o wchisptool `pkg-config --cflags --libs libusb-1.0`

clean:
	rm -f wchisptool

install: wchisptool
	cp wchisptool $(DESTDIR)/wchisptool

