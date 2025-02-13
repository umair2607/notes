___
- BIOS(Basic input output system) and UEFI(Unified  extensible firmware interface) are interfaces between hardware and OS.
- In BIOS first sector of hard drive is boot sector where MBR lives. 
- MBR has its limitations.
- In UEFI a whole boot partition is present.
- GRUB2 is a boot loader.
- GRUB2 can boot ISO, USB, UUID.
- It has a hidden boot menu which can be accessed by holding shift on boot time.
- It's configuration is located in `/boot/grub/grub.cfg`.
- Linux can booted using many different methods:
	- PXE(Over the network using TFTP).
	- IPXE(Over the network using http).
	- USB.
	- Hard drive.
	- CD.
- Linux boot process steps:
	- BIOS/UEFI gives control to GRUB/GRUB2.
	- GRUB2 locates a compressed version of Linux kernel like `vmlinux` or `vmlinuz`.
	- vmlinuz uses `initrd` files to get to file system and kernel modules.
	- vmlinuz uses initramfs and dracut as built in kernel file systems.
	- After locating and loading kernel modules a full kernel is started.
- Kernel modules are located in `/lib/modules`.
- Kernel panics can happen due to hardware issue or updating kernel to a new version.
- If updating caused kernel panic we can simply use grub to load previous kernel.
- Linux kernel is modeler.
- It loads modules dynamically when it sees their is a need for a module.
- Their is a dependency check happening in background for modules.
- Modules can be blacklisted.
- Linux kernel automatically detects hardware and loads appropriate modules.
- Blacklist modules can be found and edited in `/etc/modprobe.d`.
- While loaded modules can be found and edited in `/etc/modules-load.d/`.
- `insmod` can be used to load kernel modules in a running kernel. But it does not perform any dependency check.
- `modprobe` cab used to load kernel modules using only name and it performs all dependency checks and than uses `insmode` to load module.
- `rmmod` can be used to remove kernel modules.
- After inserting any new kernel module `depmod` should be used to updated dependency map so `modprobe` can have updated dependency map.
- `lsmod` can be used to list kernel modules.
___
