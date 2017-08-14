# Fern Linux

Fern Linux is based on Arch Linux and is currently in alpha. The goal of this distribution is to have a live distro I can use to clone disks or recover files with programs such as ddrescue.

You can download the most current image [here](https://mega.nz/#!opZhGASQ!bNK1CYXypxevm5anUvC8BQeTQRzfq4oPbqP93oGQd0Y).

The default username/password is green/green.

## Cloning disks with `ddrescue`

`ddrescue` is nice because if it runs into a block it can't read, it will check it a couple of times before just skipping it, instead of completely stopping the copy because it can't read a portion of the disk.

Here's a general run through of how you'd use it:

- Open up a terminal (`rxvt-unicode` is one that is installed on Fern).

- Find what your source drive is called. Run `lsblk` to find that. Here's an example from my computer:

```
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0 238.5G  0 disk 
├─sda1   8:1    0   499M  0 part 
├─sda2   8:2    0   128M  0 part 
├─sda3   8:3    0 228.9G  0 part 
├─sda4   8:4    0   801M  0 part 
└─sda5   8:5    0   8.2G  0 part 
sdb      8:16   1 115.7G  0 disk 
├─sdb1   8:17   1 488.3M  0 part /boot
└─sdb2   8:18   1  29.3G  0 part /
```

Here you'll see that my main drive (sda) has five partitions, and that my usb drive (sdb) has two.

- Now you can run `ddrescue`. Her

`sudo ddrescue /dev/sda 
