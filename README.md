# datasilo

Build a home server that adds high speed storage and upload capacity to a global volunteer science network

**Work in progress**

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

- Install Hyper.app or use existing Terminal
- SSH in and install node and svalbard
