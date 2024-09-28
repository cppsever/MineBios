# MineBios
Download Link (1.89 mb iso): 

[![Download MineBios](https://a.fsdn.com/con/app/sf-download-button)](https://sourceforge.net/projects/minebios/files/latest/download)

Or Floppy Disk (1.44 mb):
https://github.com/cppsever/MineBios/raw/main/MineBios.img

![png](https://github.com/cppsever/MineBios/blob/main/photo/1.png)
![png](https://github.com/cppsever/MineBios/blob/main/photo/2.png)

And You can try:

Virtual-box or Qemu:

```
qemu-system-x86_64 -boot d -cdrom MineBios.iso -m 512
```

## Features
> ✅ 100% Assembly
> 
> ✅ Movement
> 
> ✅ Basic physics
> 
> ✅ Interaction
> 
> ~ Only supported bios pc or vm
>
> ✅ Supported Qemu and Virtual-Box (May not support in the newest versions) 
>
> ✅ VGA renderer 

I couldn't try it on real hardwares but someone managed to run it in grub2 mode on Ventoy .d

## Compiling

Normal:

```
make
```

Iso compiling:

```
make iso
```

But you need:

```
sudo pacman -S qemu qemu-full cdrtools make nasm
```

## Editor

You can modify the game with these editors:

> Image Editor : https://www.drawtoarray.free.nf/index1.html

In this image editor, add the code of your x=40 y=40 work to the bottom line. And adapt it to the function on line 285.

```
db_to_tx_namer:
    cmp [di], byte 7
    je .water
(...)
    .water:
        mov si, tx_water
        jmp .done
(...)
tx_water: db (...)
```

And try your block with the start of the start_camera function

```
start_camera:
    mov [chunk+450*49+448], byte 7
```


> Map Editor : https://www.drawtoarray.free.nf/index2.html

When drawing, make x=450 y=100. Replace the code with `chunk`

## BTW

```diff
+ Actually the game itself (including texture and world) is 0.06 mb, but due to the Fat 12 file system it is at least 1.44 mb
```

## And...

```diff
- This is the first and last version of the project. There will be no further updates. :(
```

## Thanks For Character Texture

[SadikKidas](https://github.com/SadikKidas)

![png](https://github.com/cppsever/MineBios/blob/main/photo/3.png)
