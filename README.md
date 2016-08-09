# ramdisk_z3c

You can extract and compress a ramdisk in many ways, but here's what I've found works every time:

1. Extract kernel.sin from stock FTF, flash it to your PC, then pull the raw boot partition to your PC

2. Use letama's sksplit on the raw image file

3. Extract the ramdisk (usually sec1-xxx) using `cat ../ramdisk.img | gzip -d | cpio -i --make-directories`

4. Make your changes and compress with mkbootfs
