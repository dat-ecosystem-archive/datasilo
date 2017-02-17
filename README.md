# datasilo

Build a home server that adds high speed storage and upload capacity to a global volunteer science network

**Work in progress!**

If you want to build a DataSilo, you can use your own hardware or use our recommended hardware below!

If you are ready to run the software, hold on for a little while and keep an eye on [svalbard](https://github.com/datproject/svalbard), which is currently being worked on!

## Recommended Parts List

You can use any hardware but these are ones that we've tested and work great:

- [Server: Intel Compute Stick V2 (~$125)](https://www.amazon.com/gp/product/B01AZC4NHS/ref=as_li_tl?ie=UTF8&tag=datproject-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B01AZC4NHS&linkId=df633291eb6a1066699506cba2987ac2)
- [Hard Drive: WD MyBook 4TB (~$110)](https://www.amazon.com/gp/product/B01LQQHL4E/ref=as_li_tl?ie=UTF8&tag=datproject-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B01LQQHL4E&linkId=82948e95904232adfce2cf1b7caaf725)
- [Hard Drive: WD MyBook Duo 16TB (~$499)](https://www.amazon.com/gp/product/B01B6BN1CU/ref=as_li_tl?ie=UTF8&tag=datproject-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B01B6BN1CU&linkId=0e7415c88239907dba15a73be9ef6fb4)
- (Optional) [Anker USB3/Gigabit Ethernet Hub ($25)](https://www.amazon.com/gp/product/B014ZOJX7W/ref=as_li_tl?ie=UTF8&tag=datproject-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B014ZOJX7W&linkId=73bc96dfe36120b60846299d07d689d7)

If you're in Canada here's the best link we've found for the compute stick: http://www.ncix.com/detail/intel-compute-stick-stk1aw32sc-atom-6e-134117.htm

## Running Ubuntu on the Compute Stick

The Compute Stick comes with Windows. You can choose to use Windows if you prefer, the Svalbard software *should* run on it (check the Svalbard readme first, work in progress). You can also dual-boot Ubuntu pretty easily.

### Known issues

- Sandisk branded SD cards don't work under Ubuntu
- Sometimes randonly when booting the ubuntu bootloader hangs on a purple screen and requires a power cycle

## Dual boot instructions

- Download Image: http://www.linuxium.com.au/how-tos/runningubuntuontheintelcomputestick
- Use Etcher to put it on a USB Flash Drive: http://etcher.io/
- Boot from USB Stick on Compute Stick using F10 at startup. (You may need to configure the compute stick to boot in Windows 64 mode, which is done by configuring the BIOS using F2 at startup)
- Choose 'Install Ubuntu' and follow instructions to dual boot Windows with a 10GB split partition.

Helpful Youtube: https://www.youtube.com/watch?v=KAMcr2vbOsA

## Setting up the external hard drive

These instructions are for MyBook or MyBook DUO

1. install WD Drive Utilities on Mac OS
2. convert to JBOD/EXFAT and turn off Drive Sleep
3. plug into linux

```
lsblk # to view drives and get the /dev/sd<num> entries
sudo parted /dev/sd<num>
print
rm 1 (and others)
mklabel gpt
unit TB
mkpart primary 0.00TB 8.00TB
print
quit
```

Change `8.00TB` above to match the drive size depending on which drive you got

then `sudo mkfs.ext4 /dev/sd<num>` and use the UUID to generate fstab entries:

```
UUID=<UUIDHERE> /media/hd1 ext4 defaults 0 0
```

then `sudo mount -a` to reload fstab and mount (mkdir your mountpoints first)

## Running `svalbard` on your server

NOTE Svalbard is still under construction. If you are an early adopter and here already, try seeding this dat (9GB of [White House Open Datasets](https://twitter.com/denormalize/status/831581871230193664)):

```
npm install dat -g
dat clone 6fa91405f280c30cedd461dfcd3b4fffffb27759e26f8135b7cbdfe08870ccb2 eop-gov
cd eop-gov
dat sync # to seed
```

See https://github.com/datproject/svalbard for instructions when svalbard is ready

## Alternative Hardware

Here are devices we tested but for various reasons weren't as good of a fit as the Compute Stick, though YMMV and suggestions are always welcome as the DataSilo is a very hackable, DIY concept.

## NAS Boxes

If you have a NAS you can use it! But buying a full NAS might be a little overkill if you are just using your computer solely as a DataSilo.

Requirements are:

- Has gigabit ethernet
- Runs Linux and Dat (`npm install dat -g`), we use libsodium and leveldb native modules
- Allows JBOD (RAID is not needed with Svalbard/DataSilo as Dat acts as an internet-level RAID)

## Mediasonic Probox Enclosure

These are a great way to get a 4 drive JBOD bay (non-RAID). I actually have 2 of them (8 drives total, with 4TB drives). But compared to the 16TB MyBook Duo the price for these wasn't worth it! But could be a great option if you have existing drives you want to use.

## Banana Pi M1

$40

MicroSD
http://www.banana-pi.org/m1-download.html Ubuntu Mate 16.04
Limitations: Slow CPU encryption

## ODROID XU4

$80

http://odroid.in/ubuntu_16.04lts/ubuntu-16.04-mate-odroid-x2-20160920.img.xz Ubuntu Mate 16.04

Limitations: Loud Fan, slow CPU encryption

## Raspberry Pi

$30

Limitations: 100Mb Ethernet, USB2, slow CPU encryption

## Intel NUC

~$200 and up

Limitations: Many kits barebones (requires more setup), expensive, but speed/performance was good. A great option for a more general purpose machine, but Compute Stick is same thing in smaller, more limited but cheaper package.

