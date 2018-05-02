This builds a rootfs-<arch>.cpio that can be attached to the kernel
during linking and used as a RAM-only rootfs. Ain't it great.
It builds initramfs disks for a few select ARM systems plus Intel
i486 actually (because I happened to need an i486 ramfs).

Download and unpack dependencies directly into the dir where you
clones this script. (One day I may add wget downloading!)

- Main script is generate-cpio-rootfs.sh
  You does no need to read and understand this script.
  Only follow these steps and could make a rootfs.

- The etc/ directory contain some files and variants of files
  that will end up in /etc on the ramdisk

- You will need to download and install the referenced cross
  compilers, busybox and strace versions.

  1. run "make -f toolchains.mk" to fetch all the cross compile tool 
     chains.
  2. set env : CROSS_COMPILE. Set to the ./toolchians/path/to/toolchains/
  3. cd to tools directory, make;sudo make install. 
     install the gen_init_cpio tool.
  4. ./generate-cpio-rootfs.sh fvp|hikey|...
  5. generate the rootfs in current directory.
