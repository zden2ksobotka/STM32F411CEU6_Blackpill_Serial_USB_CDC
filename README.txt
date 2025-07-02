USBCCD pro "WA BlackPill STM32F411CEU6".

Zkompilovani, do bootloaderu (nahravani programu) se leze pres boot+drzeni_boot_+zmackunti_rest+pusteni boot:
	make clean && make -j$(nproc)
	sudo dfu-util -l
	dfu-util -a 0 -s 0x08000000:leave -D program.bin

Pro debug v Assembleru:
	arm-none-eabi-objdump -D program.elf
	arm-none-eabi-size program.elf

Pripojeni na usbc, serial konzole:
	picocom -b 115200 /dev/ttyACM0

