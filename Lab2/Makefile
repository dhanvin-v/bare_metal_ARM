mem_alloc.bin: mem_alloc
	arm-none-eabi-objcopy -O binary mem_alloc mem_alloc.bin

mem_alloc: mem_alloc.ld mem_alloc.o startup.o syscalls.o
	arm-none-eabi-gcc -nostdlib -T mem_alloc.ld mem_alloc.o startup.o syscalls.o ../../../../Downloads/newlib-2.5.0/arm-none-eabi/newlib/libc.a /usr/lib/gcc/arm-none-eabi/9.2.1/libgcc.a -o mem_alloc

syscalls.o: syscalls.c
	arm-none-eabi-gcc -mcpu=cortex-a8 -I ./../../../../Downloads/newlib-2.5.0/newlib/libc/include -c -o syscalls.o syscalls.c

startup.o: syscalls.c
	arm-none-eabi-as -mcpu=cortex-a8 -o startup.o startup.s

mem_alloc.o: mem_alloc.c
	arm-none-eabi-gcc -mcpu=cortex-a8 -I ./../../../../Downloads/newlib-2.5.0/newlib/libc/include -c -o mem_alloc.o mem_alloc.c

clean:
	rm *.o mem_alloc mem_alloc.bin
