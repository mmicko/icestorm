include ../config.mk
MXEGCC = /usr/local/src/mxe/usr/bin/i686-pc-mingw32-gcc

ifeq ($(STATIC),1)
LDFLAGS += -static
endif

all: $(BUILD_PREFIX)icepack$(EXE) $(BUILD_PREFIX)iceunpack$(EXE)

$(BUILD_PREFIX)icepack$(EXE): icepack.o
	$(CXX) -o $@ $(LDFLAGS) $^ $(LDLIBS)

$(BUILD_PREFIX)iceunpack$(EXE): $(BUILD_PREFIX)icepack$(EXE)
	ln -sf $(BUILD_PREFIX)icepack$(EXE) $(BUILD_PREFIX)iceunpack$(EXE)

$(BUILD_PREFIX)iceunpack.exe:
	# no iceunpack.exe, use icepack -u

install: all
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp $(BUILD_PREFIX)icepack$(EXE) $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)icepack$(EXE)
	ln -sf $(BUILD_PREFIX)icepack$(EXE) $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)iceunpack$(EXE)

uninstall:
	rm -f $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)icepack$(EXE)
	rm -f $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)iceunpack$(EXE)

clean:
	rm -f $(BUILD_PREFIX)icepack$(EXE)
	rm -f $(BUILD_PREFIX)iceunpack$(EXE)
	rm -f $(BUILD_PREFIX)icepack.exe
	rm -f *.o *.d

-include *.d

.PHONY: all install uninstall clean

