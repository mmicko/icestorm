include ../config.mk

ifeq ($(STATIC),1)
LDFLAGS += -static
endif

all: $(BUILD_PREFIX)icemulti$(EXE)

$(BUILD_PREFIX)icemulti$(EXE): icemulti.o
	$(CXX) -o $@ $(LDFLAGS) $^ $(LDLIBS)

install: all
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp $(BUILD_PREFIX)icemulti$(EXE) $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)icemulti$(EXE)

uninstall:
	rm -f $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)icemulti$(EXE)

clean:
	rm -f $(BUILD_PREFIX)icemulti$(EXE)
	rm -f $(BUILD_PREFIX)icemulti.exe
	rm -f *.o *.d

-include *.d

.PHONY: all install uninstall clean

