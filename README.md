# aosp-notes
Notes on Android internals.

---

## Partitions

Partitions:

- Android often has dozens of partitions.
- Most are not mounted during regular use.
- Most are used for recovery or system components.
- The user can only write to the `/data` partition.
- The GUID Partition Table (GPT) is used.

Filesystems:

- eMMC and MMC devices use ext4 filesystem.
- F2FS (Flash Friendly File System) is now more common.
- F2FS is log structured and optimized for NAND flash.

Standard Android partitions:

- boot, bootimg: kernel + initramfs.
- cache, ext4: updates and recovery.
- recovery, bootimg: kernel + alternate initramfs.
- system, ext4: os binaries and framework.
- userdata, ext4/f2fs: user data and configuration.


Qualcomm MSM partitions:

- aboot, bootldr: Android Boot Loader.
- modem, MSDOS: ELFs and data to support device modem.
- modemst, proprietary: non-volatile modem data.
- rpm, ELF 32-bit: first stage bootloader.
- sbl, proprietary: Secondary Boot Loader.
- tz, ELF 32-bit: ARM TrustZone.


Vendor-specific partitions:

- hboot, HTC: boot loader.
- efs, Samsung: Encrypted File System.
- ssd, Samsung: Secure Software Download.
- ota, fota, Samsung: over the air.
- grow, Samsung/LG: empty, allows partition growth.
- laf, LG: alternate bootimg for re-flashing device.
- imgdata, LG: RLE images in IMAGEDATA, like BOOTLDR.



