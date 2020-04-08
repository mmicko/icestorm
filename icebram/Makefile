include ../config.mk

ifeq ($(STATIC),1)
LDFLAGS += -static
endif

all: $(BUILD_PREFIX)icebram$(EXE)

$(BUILD_PREFIX)icebram$(EXE): icebram.o
	$(CXX) -o $@ $(LDFLAGS) $^ $(LDLIBS)

test: $(BUILD_PREFIX)icebram
	bash rundemo.sh

install: all
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp $(BUILD_PREFIX)icebram$(EXE) $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)icebram$(EXE)

uninstall:
	rm -f $(DESTDIR)$(PREFIX)/bin/$(BUILD_PREFIX)icebram$(EXE)

clean:
	rm -f $(BUILD_PREFIX)icebram$(EXE)
	rm -f $(BUILD_PREFIX)icebram.exe
	rm -f demo.* demo_*.*
	rm -f *.o *.d

-include *.d

.PHONY: all test install uninstall clean

