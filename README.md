# Using standard C libraries on bare-metal ARM
This assignment was done for the course of Advanced Embedded Systems ECGR-5101.
## Outcomes:
- Install a embedded version of a standard C library
- Examine a minimal implementation of system calls needed to support the C
library
- Use GNU Make
- Use the strace utility in Linux to monitor system calls.

### Steps:
- Using Newlib C library when dealing with embedded software, we often use standard C functions such as: printf, malloc, getchar, strncpy etc. <br>
- A common way to have them is using Newlib. <br>
Newlib is an implementation of the standard C library that is specifically designed to run on a platform with low resources and undefined hardware. <br>
- The idea of Newlib is to implement the hardware-independent parts of the standard C library and rely on few low-level system calls that must be implemented with the target hardware in mind.<br>
### To Do
Do the following:
- [X] Use the GNU make utility to implement all the compiling and linking steps given above. For more information, http://www.gnu.org/software/make/manual/make.html
- [X] The implementation of read system call in syscalls.c polls when the receive FIFO
is empty. Modify the write system call so that it polls when the transmit FIFO is full.
- [X] Write a version of mem alloc.c for x86/Linux. Trace the system calls made using the strace Linux utility. Compare the system call trace obtained to those from executing a static binary (compile with -static flag).