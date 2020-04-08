include ../config.mk

ifeq ($(STATIC),1)
LDFLAGS += -static
endif

all: $(BUILD_PREFIX)icepll$(EXE)

$(BUILD_PREFIX)icepll$(EXE): icepll.o
	$(CXX) -o $@ $(LDFLAGS) $^ $(LDLIBS)

install: all
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp $(BUILD_PREFIX)icepll$(EXE) $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)icepll$(EXE)

uninstall:
	rm -f $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)icepll$(EXE)

clean:
	rm -f $(BUILD_PREFIX)icepll$(EXE)
	rm -f $(BUILD_PREFIX)icepll.exe
	rm -f *.o *.d

-include *.d

.PHONY: all install uninstall clean

