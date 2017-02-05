

#U-Boot Compilation for 2013 Kernel

Follow these instruction up untill 'git checkout 2015.10.fslc-qdl'

https://www.udoo.org/docs/Advanced_Topics/Compile_U-Boot_Bootloader.html


Then execute these instructions :
```
cp include/configs/udoo_qdl.h include/configs/udoo_qdl.h.orig
sed -i 's|fatload|ext4load|' include/configs/udoo_qdl.h
sed -i 's|bootz|bootm|' include/configs/udoo_qdl.h


cp arch/arm/imx-common/cpu.c arch/arm/imx-common/cpu.c.orig
cp cpu.c arch/arm/imx-common/cpu.c 

cp tools/logos/udoo.bmp tools/logos/udoo.bmp.orig
cp ixor_logo.bmp tools/logos/udoo.bmp

```

continue with compilation and writing the bootloader to sdcard now..

Finally copy this file to the root of sdcard (filesystem with /boot on it) :
```
cp uEnv.txt /media/{username}/UDOObuntu
```
