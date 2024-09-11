# MineBios
Download Link: https://sourceforge.net/projects/minebios/

![png](https://github.com/cppsever/MineBios/blob/main/photo/1.png)
![png](https://github.com/cppsever/MineBios/blob/main/photo/2.png)

## Features
> ✅ 100% Assembly
> 
> ✅ Movement
> 
> ✅ Basic physics
> 
> ✅ Interaction
> 
> ~ Only supported bios x32 pc or vm
>
> ✅ Supported Virtual-Box and Qemu
>
> ✅ VGA renderer 

I haven't tried with real hardware but you can try with ventoy

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

## And...

```diff
- This is the first and last version of the project. There will be no further updates. :(
```
