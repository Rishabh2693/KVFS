Secure Key Value File System
Secure Key Value File system uses the FUSR library to create a file system with md5 hashing. The filesystem does not follow a hierarchical 
structure like our usual file systems. SKVFS uses a flat file structure as explained in the Google File System paper. 

The following code implements a file system using FUSE library.

FUSE (Filesystem in Userspace) is an interface for userspace programs to export a filesystem to the Linux kernel. The FUSE project consists
of two components: the fuse kernel module (maintained in the regular kernel repositories) and the libfuse userspace library (maintained in 
is repository). libfuse provides the reference implementation for communicating with the FUSE kernel module. A FUSE file system is 
typically implemented as a standalone application that links with libfuse. libfuse provides functions to mount the file system, unmount 
it,read requests from the kernel, and send responses back. libfuse offers two APIs: a "high-level", synchronous API, and a "low-level" 
asynchronous API. In both cases, incoming requests from the kernel are passed to the main program using callbacks. When using the high-
level API, the callbacks may work with file names and paths instead of inodes, and processing of a request finishes when the callback 
function returns. When using the low-level API, the callbacks must work with inodes and responses must be sent explicitly using a separate
set of API functions.

RUNNING THE CODE
->sudo make clean 
->sudo make 
->sudo make install

->cd src

->./kvfs
