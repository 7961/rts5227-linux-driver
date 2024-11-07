General Information
===================

Linux driver for Realtek PCI-Express card reader chip.
Debain12 kernel 6.1.0-26 Test Pass.

Build Steps
===========

1) copy to /usr/src/rts5227-1.07/
2) dkms add -m rts5227 -v 1.07
3) dkms install -m rts5227 -v 1.07
4) update-initramfs -u
5) echo 'blacklist rtsx_pci' >> /etc/modprobe.d/blacklist.conf
5) reboot your computer

Note: Root privilege is required in step 2 , 3  , 4

If you wanna unload the module after suspend, run the following command:

```bash
$ echo SUSPEND_MODULES="rts5227" | sudo tee -a /etc/pm/config.d/modules
```