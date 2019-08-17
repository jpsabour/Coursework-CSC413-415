# CSC 415 - Project 2 - File copy

## Student Name : John Sabour

## Student ID   : 917832180

## Build Instructions

1. navigate to the project folder using the "cd" command.
2. use command gcc -I -Wall filecopy.c -o fc

## Run Instructions

1. while still in the project folder, after building, use command "./fc"

## strace/dtruss output


csc415@csc415:~/Desktop/p2$ strace ./fc
execve("./fc", ["./fc"], 0x7ffcedaf4200 /* 49 vars */) = 0
brk(NULL)                               = 0x563a1a5de000
access("/etc/ld.so.nohwcap", F_OK)      = -1 ENOENT (No such file or directory)
access("/etc/ld.so.preload", R_OK)      = -1 ENOENT (No such file or directory)
openat(AT_FDCWD, "/etc/ld.so.cache", O_RDONLY|O_CLOEXEC) = 3
fstat(3, {st_mode=S_IFREG|0644, st_size=99351, ...}) = 0
mmap(NULL, 99351, PROT_READ, MAP_PRIVATE, 3, 0) = 0x7f32cadaa000
close(3)                                = 0
access("/etc/ld.so.nohwcap", F_OK)      = -1 ENOENT (No such file or directory)
openat(AT_FDCWD, "/lib/x86_64-linux-gnu/libc.so.6", O_RDONLY|O_CLOEXEC) = 3

//here we can see that our file is being read
read(3, "\177ELF\2\1\1\3\0\0\0\0\0\0\0\0\3\0>\0\1\0\0\0\260\34\2\0\0\0\0\0"..., 832) = 832
fstat(3, {st_mode=S_IFREG|0755, st_size=2030544, ...}) = 0
mmap(NULL, 8192, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0x7f32cada8000
mmap(NULL, 4131552, PROT_READ|PROT_EXEC, MAP_PRIVATE|MAP_DENYWRITE, 3, 0) = 0x7f32ca7ab000
mprotect(0x7f32ca992000, 2097152, PROT_NONE) = 0
mmap(0x7f32cab92000, 24576, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x1e7000) = 0x7f32cab92000
mmap(0x7f32cab98000, 15072, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_ANONYMOUS, -1, 0) = 0x7f32cab98000
close(3)                                = 0
arch_prctl(ARCH_SET_FS, 0x7f32cada9500) = 0
mprotect(0x7f32cab92000, 16384, PROT_READ) = 0
mprotect(0x563a1a001000, 4096, PROT_READ) = 0
mprotect(0x7f32cadc3000, 4096, PROT_READ) = 0
munmap(0x7f32cadaa000, 99351)           = 0
fstat(1, {st_mode=S_IFCHR|0620, st_rdev=makedev(136, 0), ...}) = 0
brk(NULL)                               = 0x563a1a5de000
brk(0x563a1a5ff000)                     = 0x563a1a5ff000
//it is printing out our strings to start the program off
write(1, "Welcome to the File Copy Program"..., 49Welcome to the File Copy Program by John Sabour!
) = 49
write(1, "Enter the name of the file to co"..., 41Enter the name of the file to copy from:
) = 41
fstat(0, {st_mode=S_IFCHR|0620, st_rdev=makedev(136, 0), ...}) = 0
read(0, 



