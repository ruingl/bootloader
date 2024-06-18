NASM = nasm
DD = dd
SRC_DIR = BOOT
BUILD_DIR = BUILD
BOOT_SRC = $(SRC_DIR)/BOOT.asm
BOOT_BIN = $(BUILD_DIR)/BOOT.bin
BOOT_FLP = $(BUILD_DIR)/boot.flp

all: $(BOOT_FLP)

$(BOOT_BIN): $(BOOT_SRC)
	$(NASM) -f bin -o $@ $<

$(BOOT_FLP): $(BOOT_BIN)
	$(DD) status=noxfer conv=notrunc if=$< of=$@

clean:
	rm -f $(BOOT_BIN) $(BOOT_FLP)

.PHONY: all clean
