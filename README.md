# ramdisk_z3c

For each device (so far only aries), the directory includes a raw boot partition image, as well as the ramdisk, extracted with sksplit. There's also a directory that contains the completely extracted ramdisk.

You can extract and compress a ramdisk in many ways, but here's what I've found works every time:

1. Extract kernel.sin from stock FTF, flash it to your phone, then pull the raw boot partition to your PC

2. Use letama's sksplit on the raw image file

3. Extract the ramdisk (usually sec1-xxx) using `cat ../sec1-0x02000000.bin | gzip -d | cpio -i --make-directories`

4. Make your changes and compress with `mkbootfs DIR | gzip -n -f > ramdisk.img`
