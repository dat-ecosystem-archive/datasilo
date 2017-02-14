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

## Running Ubuntu on the Compute Stick

Download Image: http://www.linuxium.com.au/how-tos/runningubuntuontheintelcomputestick

TODO have pre-baked image

Use Etcher to put it on a USB Flash Drive: http://etcher.io/

Install Ubuntu in a 10GB split partition.

Helpful Youtube: https://www.youtube.com/watch?v=KAMcr2vbOsA

Add HD to fstab

## Running `svalbard` on your server

See https://github.com/datproject/svalbard for instructions

## Alternative Hardware

Here are devices we tested but for various reasons weren't as good of a fit as the Compute Stick, though YMMV and suggestions are always welcome as the DataSilo is a very hackable, DIY concept.

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
