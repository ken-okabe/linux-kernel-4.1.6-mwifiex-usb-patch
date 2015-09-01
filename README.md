# linux-kernel-4.1.6-mwifiex-usb-patch

[Bug 69661 - mwifiex_usb on MS Surface Pro 1 is unstable](https://bugzilla.kernel.org/show_bug.cgi?id=69661) patch applied kernel how to


Download stable kernel-4.1.* source(tar.xz) from
[https://www.kernel.org/](https://www.kernel.org/)

2 files under linux-4.1.6_mwifiex_usb to be modified (replace these files to the downloaded kernel source files)

the file path

- drivers/net/wireless/mwifiex/usb.c

- drivers/usb/host/xhci-ring.c


$ sudo apt install kernel-package

create a working dir

$ mkdir linux-4.1.6_mwifiex

copy the whole files to the working dir

$ cp /boot/config-current-kernel-version linux-4.1.6_mwifiex/.config

move to the working dir

$ cd linux-4.1.6_mwifiex

$ make oldconfig

$ fakeroot make-kpkg --initrd kernel_image kernel_headers --append_to_version=4.1.6-mwifiex --revision=1 -j 5


The attached deb files were compiled under Debian8.1 jessie 64bit


Install them.

$ sudo dpkg -i linux-headers-4.1*.deb linux-image-4.1*.deb

sudo reboot


To uninstall,

sudo apt-get remove 'linux-headers-4.1*' 'linux-image-4.1*'
