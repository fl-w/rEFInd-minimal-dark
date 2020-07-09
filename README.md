## Minimal dark rEFInd theme

This theme is based on [rEFInd-minimal] but improved for darker environments.

[rEFInd](http://www.rodsbooks.com/refind/) is an easy to use boot manager for UEFI
based systems. This is a clean and minimal theme for it.

![rEFInd-minimal-dark-screenshot](https://user-images.githubusercontent.com/30976147/87032792-08ee7580-c1dd-11ea-9877-74c48c489726.png)

### Usage

 1. Locate your refind EFI directory. This is commonly `/boot/EFI/refind`
    though it will depend on where you mount your ESP and where rEFInd is
    installed. `fdisk -l` and `mount` may help.

 2. Create a folder called `themes` inside it, if it doesn't already exist

 3. Clone this repository into the `themes` directory.

 4. To enable the theme add `include themes/rEFInd-minimal-dark/theme.conf` at the end of
    `refind.conf`.

Here's an example menuentry configuration (from the screenshot)

```nginx
menuentry "Arch Linux" {
	icon /EFI/refind/themes/rEFInd-minimal-dark/icons/os_arch.png
	loader vmlinuz-linux
	initrd initramfs-linux.img
	options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
	icon /EFI/refind/themes/rEFInd-minimal-dark/icons/os_win.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "Ubuntu" {
	icon /EFI/refind/themes/rEFInd-minimal-dark/icons/os_ubuntu.png
	options "rw root=UUID=c1ffd0ad-60bc-45cb-8e2c-00d863b96d39 logLevel=3"
}
```

Entries that are autodetected should also show the proper icons.

### Background sizes

If you find the background looks blurry it may be due to the included wallpaper
being an incorrect resolution for your monitor. You can download the [original
wallpaper][wallpaper], resize it as appropriate, and replace the
`background.png`.

You can of course also choose your own background!

### Attribution

The recolored OS icons are from [Lightness for burg][icons] by [SWOriginal][icon-author].

[rEFInd-minimal]: https://github.com/EvanPurkhiser/rEFInd-minimal

[wallpaper]: https://github.com/folws/rEFInd-minimal-dark/raw/master/background.png

[icons]: http://sworiginal.deviantart.com/art/Lightness-for-burg-181461810
[icon-author]: http://sworiginal.deviantart.com/
